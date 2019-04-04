---
title: Neighborhoods of San Francisco
author: dm4fn
excerpt: '[Cross-posted from dclure.org] View the Exhibit Built on the Stamen Toner layer. Back in October, about a month after moving from Scholars&rsquo; Lab HQ in Virginia out to Menlo Park (my partner started a PhD program at Stanford), I drove up the peninsula to San Francisco on a Saturday morning and set out on a&hellip;. <a href="http://www.scholarslab.org/geospatial-and-temporal/neatline-san-francisco/">More.</a>'
layout: post
permalink: /2013/12/11/neighborhoods-of-san-francisco/
enclosure:
  - |
    |
        
        
        
syndication_source:
  - 'Scholars&#039; Lab » neatline'
syndication_source_uri:
  - http://www.scholarslab.org
syndication_source_id:
  - http://www.scholarslab.org/tag/neatline/feed
"rss:comments":
  - 'http://www.scholarslab.org/geospatial-and-temporal/neatline-san-francisco/#comments'
"wfw:commentRSS":
  - http://www.scholarslab.org/geospatial-and-temporal/neatline-san-francisco/feed/
syndication_feed:
  - http://www.scholarslab.org/tag/neatline/feed
syndication_feed_id:
  - 8
syndication_permalink:
  - http://www.scholarslab.org/geospatial-and-temporal/neatline-san-francisco/
syndication_item_hash:
  - 1c37ebbf2a3a4795932700b4273a5de5
  - aff49ccbc9958be6525bb10e7c765e74
categories:
  - Geospatial and Temporal
  - neatline
---
<span class="Z3988" title="ctx_ver=Z39.88-2004&rft_val_fmt=info%3Aofi%2Ffmt%3Akev%3Amtx%3Adc&rfr_id=info%3Asid%2Focoins.info%3Agenerator&rft.type=&rft.format=text&rft.title=Neighborhoods+of+San+Francisco&rft.source=Scholars%26%23039%3B+Lab&rft.date=2013-12-11&rft.identifier=http%3A%2F%2Fwww.scholarslab.org%2Fgeospatial-and-temporal%2Fneatline-san-francisco%2F&rft.language=English&rft.subject=Geospatial+and+Temporal&rft.aulast=McClure&rft.aufirst=David"></span> 
*[Cross-posted from [dclure.org][1]]*

## [View the Exhibit][2]

[<img src="http://dclure.org/wp-content/uploads/2013/12/neighborhoods-of-san-francisco.jpg" alt="neighborhoods-of-san-francisco" width="1000" height="980" class="alignnone size-full wp-image-3355" />][2]

<small>Built on the <a href="http://maps.stamen.com/#toner/12/37.7706/-122.3782">Stamen Toner layer</a>.</small>

Back in October, about a month after moving from Scholars&#8217; Lab HQ in Virginia out to Menlo Park (my partner started a PhD program at Stanford), I drove up the peninsula to San Francisco on a Saturday morning and set out on a long, rambling, 10-mile trek along the northwest shoulder of the city. It was a fantastic day &#8211; I walked west through Golden Gate Park, north along the Richmond beach, past the Cliff House, into the fog over Lincoln Park, through the mansions in Sea Cliff, past the abandoned artillery nests on the western coast of the Presidio, and finally out onto the Golden Gate bridge. From there, I headed south through the trails in the Presidio, into Richmond, and eventually back to where I started, near the top right corner of the park.

From the middle of the Golden Gate Bridge, you can look out to the east over a large swath of the city &#8211; the skyscrapers of the financial district, the new span of the Bay Bridge hanging over Treasure Island, Alcatraz, and the faded outline of the East Bay, the Berkeley campus a little smudge at the base of the ridge line. But, scanning my eyes over the rest of the city, I realized that I had very little sense of what I was actually looking at. I could attach labels onto all the touristy landmarks, but I didn&#8217;t have any kind of intuitive mental geography of the place &#8211; the names of all the little hills and neighborhoods, what connects to what, how to string the pieces of the city together into workable routes and itineraries.

So, over the course of the next few weeks, I slowly cobbled together a [Neatline exhibit][2] that plots out each of the neighborhoods in the city &#8211; 87 of them, by my count, although it&#8217;s somewhat a matter of interpretation as to how they should be sliced and diced. Working mainly from [this image][3] as reference, I started by tracing rough outlines of the boundaries (using Neatline&#8217;s standard-issue &#8220;Draw Polygon&#8221; tool) on top of Stamen&#8217;s Toner layer. Then, once the borders were in place, I used Neatline&#8217;s SVG import tool to place vector-geometry text labels on top of each of the individual neighborhoods, inspired by other spatial-wordcloud experiments like [this][4] and [this][5].

**Adventures in geospatial typesetting**

This was great fun, and, interestingly, it ended up overlapping in unexpected ways with the [interactive][6] [typesetting][7] [projects][8] that I was playing with earlier in the semester. The process of positioning the labels becomes a kind of textual jigsaw puzzle, a game of trying to wrangle the raw, geometric instantiations of words into a coherent organizational scheme &#8211; except, this time, against the backdrop of actual geospatial coordinates and locations, not the abstract, featureless voids of the poetry experiments. Often, this is pretty straightforward &#8211; Noe Valley and the Inner Mission, for example, just get tagged as such:

[<img src="http://dclure.org/wp-content/uploads/2013/12/noe-valley-inner-mission.jpg" alt="noe-valley-inner-mission" width="1000" height="788" class="alignnone size-full wp-image-3312" />][9]

In other places, though, the names of the neighborhoods overlap with one another in ways that make it possible to find interesting &#8220;economies&#8221; in how the words can be laid out on the map &#8211; when adjacent neighborhoods share the same words, it&#8217;s sometimes possible to essentially atomize the names into their component parts, and then rebuild them according to their own spatial logic, in a sense, by visually stringing together the pieces on the map. Take Richmond, for example, which is divided into three side-by-side segments: Outer Richmond, Central Richmond, and Inner Richmond. Instead of cluttering things up by repeating &#8220;Richmond&#8221; for each of the three sections, I just dragged out a single, all-encompassing &#8220;Richmond&#8221; across the entire width of the three sub-neighborhoods, and the blocked in the three modifiers as smaller words on top of the corresponding sections:

[<img src="http://dclure.org/wp-content/uploads/2013/12/richmond.jpg" alt="richmond" width="1000" height="412" class="alignnone size-full wp-image-3314" />][10]

This worked much the same way for the Sunset and Parkside neighborhoods, which share the same cleanly partitioned spatial organization:

[<img src="http://dclure.org/wp-content/uploads/2013/12/sunset.jpg" alt="sunset" width="1000" height="383" class="alignnone size-full wp-image-3316" />][11]

With the exception of the &#8220;middle&#8221; portion of Parkside, which is just the un-prefixed &#8220;Parkside,&#8221; meaning that the center piece doesn&#8217;t get a separate modifier:

[<img src="http://dclure.org/wp-content/uploads/2013/12/parkside.jpg" alt="parkside" width="1000" height="590" class="alignnone size-full wp-image-3318" />][12]

In other cases, though, it gets much trickier, and much more interesting. Take the little cluster of neighborhoods at the southwest corner of the Presidio, the big park at the base of the Golden Gate Bridge. It&#8217;s a hodgepodge of repeated names, but in a much more scrambled and overlapping way &#8211; Presidio, Presidio Heights, Pacific Heights, Lower Pacific Heights. In this case, I had to take a bit more care to place the little black arrows in ways that didn&#8217;t connote incorrect linkages among the names. For example, the relationship between Presidio and Presidio Heights moves in just one direction &#8211; Presidio Heights (labelled with just &#8220;Heights&#8221; on the map) needs to &#8220;inherit&#8221; the &#8220;Presidio&#8221; modifier from the Presidio, but not the other way around, since the Presidio ceases to be the Presidio when &#8220;Heights&#8221; is tacked onto it:

[<img src="http://dclure.org/wp-content/uploads/2013/12/presidio.jpg" alt="presidio" width="1000" height="467" class="alignnone size-full wp-image-3319" />][13]

To encode these relationships, I settled on a rule of thumb that the arrows would always be *contained inside the neighborhoods that they modify*. So, the arrow pointing from &#8220;Presidio&#8221; to &#8220;Heights&#8221; is fully contained inside of the geographic boundaries of Presidio Heights, in the sense that it pulls &#8220;Presidio&#8221; downward into the &#8220;Heights,&#8221; without also pushing &#8220;Heights&#8221; back in the other direction (which would effectively mislabel the Presidio). Likewise the link between &#8220;Pacific&#8221; and &#8220;Heights&#8221; is contained within the Pacific Heights outline, since otherwise Presidio Heights would be implicitly but incorrectly prefixed by &#8220;Pacific.&#8221;

Anyway, this is all completely useless as actual cartographic practice, but great fun as a kind of abstract *étude* of information design. It&#8217;s also incredibly useful as a mnemonic device &#8211; after untold hours in Palo Alto coffee shops sketching out all the outlines and positioning the labels, they&#8217;re all thoroughly burned into my mind. This is an interesting aspect of digital mapping projects that doesn&#8217;t get a lot of attention &#8211; we tend to focus on the final products, the public-facing visualizations and interactions (for good and obvious reasons), but much less on the *process* that goes into creating them, the personal acquisition of knowledge that takes place when you force yourself to spend dozens or hundreds of hours painstakingly positioning and repositioning things on maps. It gives you an incredible sense of cognitive intimacy with the space, the ability to load a little chunk of the world into working memory and reason about it in really complex and interesting ways.

 [1]: http://dclure.org/essays/neighborhoods-of-san-francisco/
 [2]: http://neatline.dclure.org/neatline/show/neighborhoods-of-san-francisco
 [3]: http://www.reocities.com/mwarren_us/sf-neighborhoods/SFNeighborhoods.gif
 [4]: http://sfsgeography.wikispaces.com/file/view/SF_neighborhhods.jpg/184285923/SF_neighborhhods.jpg
 [5]: http://www.californiatravel.eu/travel/NeighborhoodsofSanFrancisco.jpg
 [6]: http://dclure.org/essays/experimental-typesetting-with-neatline-and-shakespeare/
 [7]: http://dclure.org/essays/more-fun-with-interactive-typesetting-a-coat-by-yeats/
 [8]: http://dclure.org/essays/song-of-wandering-aengus/
 [9]: http://dclure.org/wp-content/uploads/2013/12/noe-valley-inner-mission.jpg
 [10]: http://dclure.org/wp-content/uploads/2013/12/richmond.jpg
 [11]: http://dclure.org/wp-content/uploads/2013/12/sunset.jpg
 [12]: http://dclure.org/wp-content/uploads/2013/12/parkside.jpg
 [13]: http://dclure.org/wp-content/uploads/2013/12/presidio.jpg