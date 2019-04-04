---
title: Interactive CSS in Neatline 2.0
author: dm4fn
excerpt: '[Cross-posted with dclure.org] Neatline 2.0 makes it possible to work with really large collections of records &ndash; as many as about 1,000,000 in a single exhibit. This level of scalability opens up the door to a whole range of projects that would have been impossible with the first version of Neatline, but it also introduces&hellip;. <a href="http://www.scholarslab.org/geospatial-and-temporal/interactive-css-in-neatline-2-0/">More.</a>'
layout: post
permalink: /2013/05/14/interactive-css-in-neatline-2-0-2/
syndication_source:
  - 'Scholars&#039; Lab » neatline'
syndication_source_uri:
  - http://www.scholarslab.org
syndication_source_id:
  - http://www.scholarslab.org/tag/neatline/feed
"rss:comments":
  - 'http://www.scholarslab.org/geospatial-and-temporal/interactive-css-in-neatline-2-0/#comments'
"wfw:commentRSS":
  - http://www.scholarslab.org/geospatial-and-temporal/interactive-css-in-neatline-2-0/feed/
syndication_feed:
  - http://www.scholarslab.org/tag/neatline/feed
syndication_feed_id:
  - 8
syndication_permalink:
  - http://www.scholarslab.org/geospatial-and-temporal/interactive-css-in-neatline-2-0/
syndication_item_hash:
  - 0eb508f91973d3f908e67b6f5f3efc5b
  - 3fef8409205bca802a54f2b7c239a2a5
  - a1b83c4dae59a6b8155a89b3042bc097
enclosure:
  - |
    |
        
        
        
categories:
  - CSS
  - Geospatial and Temporal
  - neatline
---
<span class="Z3988" title="ctx_ver=Z39.88-2004&rft_val_fmt=info%3Aofi%2Ffmt%3Akev%3Amtx%3Adc&rfr_id=info%3Asid%2Focoins.info%3Agenerator&rft.type=&rft.format=text&rft.title=Interactive+CSS+in+Neatline+2.0&rft.source=Scholars%26%23039%3B+Lab&rft.date=2013-05-14&rft.identifier=http%3A%2F%2Fwww.scholarslab.org%2Fgeospatial-and-temporal%2Finteractive-css-in-neatline-2-0%2F&rft.language=English&rft.subject=Geospatial+and+Temporal&rft.aulast=McClure&rft.aufirst=David"></span> 
*[Cross-posted with [dclure.org][1]]*

Neatline 2.0 makes it possible to work with really large collections of records &#8211; as many as about [1,000,000 in a single exhibit][2]. This level of scalability opens up the door to a whole range of projects that would have been impossible with the first version of Neatline, but it also introduces some really interesting content management challenges. If the map can *display* millions of records, it also needs utilities to effectively *manage* content at that scale.

This often involves a shift from working with individual records to working with groups of records. When there are a million records on the map, it&#8217;s pretty unlikely that you&#8217;ll want to change the color of just one of them. More likely, that record will exist as part of a large grouping of related records (eg, &#8220;democratic precincts,&#8221; or &#8220;photographs from 1945&#8243;), all of which should share a certain set of attributes. There needs to be a way to slice and dice records into overlapping clusters of related records, and then apply bulk updates to the individual clusters.

Really, this is a familiar problem &#8211; it&#8217;s structurally identical to the task of styling web pages with CSS, which makes it possible to address groupings of elements with &#8220;selectors&#8221; and apply key-value styling rules to the groups. Inspired by projects like Mike Migurski&#8217;s [**Cascadenick**][3], Neatline 2.0 makes it possible to use a Neatline-inflected dialect of CSS to update groups of records linked together with &#8220;tags,&#8221; which can be applied in any combination to the individual records.

**Neatline Stylesheet Basics**

Let&#8217;s take a look at how this works in practice. Imagine you&#8217;re plotting results from the last four presidential elections. You load in a big collection of 800,000 records (200,000 precincts for each of the four elections), each representing an individual polling place with a point on the map. Each point is scaled to represent the number of ballots cast at that location, and shared red or blue according to which party won more votes. In this case, there are really seven different nested and overlapping taxonomies in the data. All of the records are `precincts`, but each falls into one of the our election seasons &#8211; `2000`, `2004`, `2008`, or `2012`. And each precinct went either `democrat` or `republican`, regardless of which election cycle it belongs to. Each record can be tagged with some combination of these tags:

[<img src="http://www.scholarslab.org/wp-content/uploads/2013/05/tags-input.jpg" alt="tags-input" width="396" height="331" class="alignnone size-full wp-image-8293" />][4]

Each of the groupings needs to share a specific set of attributes &#8211; and also *not* share some attributes that need to be assigned separate values on individual records. For example, all of the precincts &#8211; regardless of date or party &#8211; should share the same basic `fill-opacity` and `stroke-width` styles. All records in each of the groupings for the four election seasons need to share the same `after-date` and `before-date` visibility settings so that the records phase in and out of visibility in unison. And all republican and democratic records should share the same shares of red and blue. Meanwhile, none of the groupings should define a standard point-radius style, which is used on a per-record basis to encode the number of ballots cast at that location.

Neatline-inflected CSS makes it easy to model these relationships. To start, I&#8217;ll define some basic styles for the top-level `precinct` tag, which is applied to all the records in the exhibit:



Now, when I click &#8220;Save,&#8221; Neatline instantaneously updates the `stroke-width` and `fill-opacity` styles on all records tagged with `precinct`:

[<img src="http://www.scholarslab.org/wp-content/uploads/2013/05/precinct-styles-1024x640.jpg" alt="precinct-styles" width="1024" height="640" class="alignnone size-large wp-image-8294" />][5]

Next, I&#8217;ll set the `before-date` and `after-date` properties for each of the for election season tags, which ensure that the four batches of records phase in and out of visibility in unison as the timeline is scrolled back and forth:



Now, when I open up any individual record, the `before-date` and `after-date` fields will be updated with new values depending on which election the record belongs to:

[<img src="http://www.scholarslab.org/wp-content/uploads/2013/05/dates-fieldset.jpg" alt="dates-fieldset" width="304" height="353" class="alignnone size-full wp-image-8295" />][6]

Last, I&#8217;ll define the coloring rules for the two political parties. First, the Democrats:



Click &#8220;Save,&#8221; and all democratic precincts update with the new color:

[<img src="http://www.scholarslab.org/wp-content/uploads/2013/05/democrat-styles-1024x640.jpg" alt="democrat-styles" width="1024" height="640" class="alignnone size-large wp-image-8296" />][7]

**Auto-updating stylesheet values**

So far, we&#8217;ve just been entering hard-coded values into the stylesheet. This often makes sense for properties that have inherently semantic values (eg, dates). For other attributes, though (namely colors), it&#8217;s much harder to reason in the abstract about what value you want. For example, I know that I want the republican precincts to be &#8220;red,&#8221; but I don&#8217;t know off-hand that `#ff0000` is the specific hexadecimal value that I want to use. It makes more sense to open up the edit form for an individual record and use the color pickers for the &#8220;Fill Color&#8221; field to find a color that looks good.

And even for styles that can be reasoned about in the abstract, it&#8217;s often easier and more intuitive to use the auto-previewing functionality on one of the record forms to tinker around with different values. Once you&#8217;ve decided on a new setting, though, it&#8217;s annoying to have to manually propagate the value back into the stylesheets so that all of the record&#8217;s siblings stay in sync &#8211; you&#8217;d have to copy the value, close the form, open up the stylesheet, find the right rule, and paste in the new value. To avoid this, Neatline also automatically updates the *stylesheet* when individual record values are changed, and immediately pushes out the new value to all of the record&#8217;s siblings.

Let&#8217;s go back to the election results. For the republican precincts, instead of pasting in a specific hex value for the `fill-color` style, we&#8217;ll just &#8220;register&#8221; `fill-color` as being one of the properties controlled by the `republican` tag by listing the style and assigning it a value of `auto`:



When I click &#8220;Save,&#8221; nothing happens, since a value isn&#8217;t defined. Now, though, I can just open up any of the individual `republican` records, choose a shade of red, and save the record. Since we activated the fill-color style for the republican tag, Neatline automatically updates all of the other `republican` records *just as if we had set the value directly on the stylesheet*:

[<img src="http://www.scholarslab.org/wp-content/uploads/2013/05/republican-record-1024x640.jpg" alt="republican-record" width="1024" height="640" class="alignnone size-large wp-image-8297" />][8]

And now, when I go back to the stylesheet, the `fill-color` rule under `republican` is automatically updated with the value that we just set in the record form:

[<img src="http://www.scholarslab.org/wp-content/uploads/2013/05/updated-stylesheet.jpg" alt="updated-stylesheet" width="304" height="593" class="alignnone size-full wp-image-8298" />][9]

This also works for styles that already have concrete values. For example, say I change my mind and want to tweak the shade of blue used for democratic precincts. I can just open up any of the individual `democrat`-tagged records, pick a new value with the color picker, and save the record. Again, Neatline automatically replaces the old value on the stylesheet and propagates the change to all of the other democratic precincts.

 [1]: http://dclure.org/uncategorized/interactive-css-in-neatline-2-0/
 [2]: http://dclure.org/logs/neatline-one-million-records/
 [3]: https://github.com/mapnik/Cascadenik
 [4]: http://www.scholarslab.org/wp-content/uploads/2013/05/tags-input.jpg
 [5]: http://www.scholarslab.org/wp-content/uploads/2013/05/precinct-styles.jpg
 [6]: http://www.scholarslab.org/wp-content/uploads/2013/05/dates-fieldset.jpg
 [7]: http://www.scholarslab.org/wp-content/uploads/2013/05/democrat-styles.jpg
 [8]: http://www.scholarslab.org/wp-content/uploads/2013/05/republican-record.jpg
 [9]: http://www.scholarslab.org/wp-content/uploads/2013/05/updated-stylesheet.jpg