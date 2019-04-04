---
title: Parent-child relationships in Neatline
author: clured
layout: post
permalink: /2012/07/19/parent-child-relationships-in-neatline/
categories:
  - Neatline News
---
One of the most powerful features in [Neatline][1], our newly-released [Omeka][2]-based tool for geo-temporal interpretation of humanities collections, is the ability to create parent-child relationships between records in an exhibit. Any record can be the parent of any other record, and there are no limits on the depth of the nesting &#8211; a parent record can itself have a parent record, and so on and so forth.

This relationship is established *from* the child *to* the parent. To set a parent record, click into the &#8220;Relations&#8221; fieldset and use the dropdown to select a record:

<a href="http://www.scholarslab.org/geospatial-and-temporal/parent-child-relationships-in-neatline/attachment/parent-record-field/" rel="attachment wp-att-5047"><img src="http://www.scholarslab.org/wp-content/uploads/2012/07/parent-record-field.jpg" alt="" title="parent-record-field" width="385" height="286" class="alignnone size-full wp-image-5047" /></a>

What&#8217;s the point of this? When you set a parent record, the child *automatically inherits all of the styling and visibility settings of the parent*. In a nutshell, this makes it possible to create &#8220;batches&#8221; of records that share a common set of styles and phase in and out of visibility in unison.

For example, imagine that you need to split the records in your exhibit into two a &#8220;blue&#8221; category and a &#8220;red&#8221; category. Instead of combing through each record and typing in the exact same lineup of styles for all the records in each of the categories, you can just create two abstract &#8220;template&#8221; records that contain the style defaults for each group and associate each of the content records with one of the templates.

With six records, three blue and three red, that would look like this:

<a href="http://www.scholarslab.org/geospatial-and-temporal/parent-child-relationships-in-neatline/attachment/blue-red-item-browser/" rel="attachment wp-att-5052"><img src="http://www.scholarslab.org/wp-content/uploads/2012/07/blue-red-item-browser.jpg" alt="" title="blue-red-item-browser" width="385" height="369" class="alignnone size-full wp-image-5052" /></a>

Blue 1, Blue 2, and Blue 3 are children of [Blue Parent], and Red 1, Red 2, and Red 3 are children of [Red Parent]:

<a href="http://www.scholarslab.org/geospatial-and-temporal/parent-child-relationships-in-neatline/attachment/blue-1/" rel="attachment wp-att-5057"><img src="http://www.scholarslab.org/wp-content/uploads/2012/07/blue-1.jpg" alt="" title="blue-1" width="382" height="288" class="alignnone size-full wp-image-5057" /></a>

And in the final exhibit, the colors are rendered correctly without ever having to set a single style on Blue 1, Blue 2, Blue 3, Red 1, Red 2, or Red 3:

  
<small>Powered by <a href="http://neatline.org/">Neatline</a> | <a href="http://sandbox.scholarslab.org/webservice/david/parent-records" target="_blank">View fullscreen</a></small>

This also works for the record visibility settings that control the date range on the timeline during which the a record is visible &#8211; the &#8220;Start Visible Date&#8221; and &#8220;End Visible Date&#8221; fields in the &#8220;Temporal&#8221; fieldset. In the example above, say that you want the blue points to be visible from 1900-1960, and the red points from 1940-2000. Set these visibility intervals on the parent records, and the child records will phase in and out of visibility in unison:

  
<small>Powered by <a href="http://neatline.org/">Neatline</a> | <a href="http://sandbox.scholarslab.org/webservice/david/parent-records-date" target="_blank">View fullscreen</a></small>

What if you need to selectively override the defaults, though? What if you want a record to inherit most style and visibility settings from upstream in the inheritance chain, but you want to adjust one or two settings to differentiate the record?

For example, imagine you want one of the blue points to be yellow &#8211; but you still want it to phase in and out of view with the other blue points. Instead of having to break away the record and re-set all of the settings just in order to make the color change, you can just directly change the color setting on the record, and all of the other unchanged settings will continue to inherit from upwards in the chain:

  
<small>Powered by <a href="http://neatline.org/">Neatline</a> | <a href="http://sandbox.scholarslab.org/webservice/david/parent-records-overrides" target="_blank">View fullscreen</a></small>

Neatline always tries to find record-specific value first, meaning that an inherited value can always be clobbered by a locally-set value (think of it as `!important` in CSS). If Neatline doesn&#8217;t find a record-specific value, it starts to traverse up the inheritance chain to the parent record(s), and stops when it finds a record-specific value on one of the parents. If none of the parents have a value for the attribute in question, then Neatline falls back on the exhibit default values, which can be configured in the &#8220;Map Settings&#8221; dropdown tab.

**Parent records in action**

How does this work with real content? The [Battle of Chancellorsville demo exhibit][3] makes heavy use of parent records. This is a complex exhibit with a lot of moving parts. There are three separate base maps, one for each of the three days of the battle &#8211; May 2, May 3, and May 4, 1863. Each of the maps has a large collection of spatial annotations and numbered waypoints that are relevant to *just one of the maps* &#8211; as the map switches out in response to the position of the timeline, the corresponding set of annotations and waypoints needs to phase into view at the same time. Meanwhile, the spatial vectors can be broken down into categories that should share similar styles &#8211; the Union and Confederate lines should all share the same shades of blue and red.

You could just go through and directly set the correct colors and visibility dates on each individual record. This is labor-intensive, though, and it tends to lock you into design decisions that you make at the beginning of the process – if you change your mind down the road and want to adjust the Union blue, you’d have to work through 50-odd records and update them individually.

Parent records make it possible to formalize the conceptual relationships and manipulate the groupings in bulk – once the correct inheritance chain is set up, you can set the style and visibility settings a single time at the top of the stack and the settings will cascade downwards to all of the children. For this exhibit, the inheritance structure looks like this:

<code style="font-size:15px;">&lt;/p>
&lt;p>&lt;strong>May 2, 1863&lt;/strong> (visible: May 2 - May 3)&lt;br />
--- &lt;strong>[may 2 condeferate lines]&lt;/strong> (color: #b52f2f)&lt;br />
-------- May annotation 1 &lt;span style="color:gray">(visible: May 2 - May 3; color: #b52f2f)&lt;/span>&lt;br />
-------- May annotation 2 &lt;span style="color:gray">(" ")&lt;/span>&lt;br />
-------- May annotation 3 &lt;span style="color:gray">(" ")&lt;/span>&lt;br />
-------- (...)&lt;br />
--- &lt;strong>[may 2 union lines]&lt;/strong> (color: #093696)&lt;br />
-------- May annotation 4 &lt;span style="color:gray">(visible" May 2 - May 3; color: #093696)&lt;/span>&lt;br />
-------- May annotation 5 &lt;span style="color:gray">(" ")&lt;/span>&lt;br />
-------- May annotation 6 &lt;span style="color:gray">(" ")&lt;/span>&lt;br />
-------- (...)&lt;/p>
&lt;p>&lt;strong>May 3, 1863&lt;/strong> (visible: May 3 - May 4)&lt;br />
--- &lt;strong>[may 3 condeferate lines]&lt;/strong> (color: #b52f2f)&lt;br />
-------- May annotation 7 &lt;span style="color:gray">(visible: May 3 - May 4; color: #b52f2f)&lt;/span>&lt;br />
-------- May annotation 8 &lt;span style="color:gray">(" ")&lt;/span>&lt;br />
-------- May annotation 9 &lt;span style="color:gray">(" ")&lt;/span>&lt;br />
-------- (...)&lt;br />
--- &lt;strong>[may 3 union lines]&lt;/strong> (color: #093696)&lt;br />
------ May annotation 10 &lt;span style="color:gray">(visible: May 3 - May 4; color: #093696)&lt;/span>&lt;br />
------ May annotation 11 &lt;span style="color:gray">(" ")&lt;/span>&lt;br />
------ May annotation 12 &lt;span style="color:gray">(" ")&lt;/span>&lt;br />
------ (...)&lt;/p>
&lt;p>&lt;strong>May 4, 1863&lt;/strong> (visible: May 4 - May 5)&lt;br />
--- &lt;strong>[may 4 condeferate lines]&lt;/strong> (color: #b52f2f)&lt;br />
-------- May annotation 13 &lt;span style="color:gray">(visible: May 4 - May 5; color: #b52f2f)&lt;/span>&lt;br />
-------- May annotation 14 &lt;span style="color:gray">(" ")&lt;/span>&lt;br />
-------- May annotation 15 &lt;span style="color:gray">(" ")&lt;/span>&lt;br />
-------- (...)&lt;br />
--- &lt;strong>[may 4 union lines]&lt;/strong> (color: #093696)&lt;br />
-------- May annotation 16 &lt;span style="color:gray">(visible: May 4 - May 5; color: #093696)&lt;/span>&lt;br />
-------- May annotation 17 &lt;span style="color:gray">(" ")&lt;/span>&lt;br />
-------- May annotation 18 &lt;span style="color:gray">(" ")&lt;/span>&lt;br />
-------- (...)&lt;/p>
&lt;p></code>

The top-level visibility dates are set on the three records that house the base maps. Under each of the three map records, abstract style records define the colors and opacities for the Union and Confederate lines. The actual content records then inherit from these records, receiving both the top-level visibility parameters on the map records and the styles on the abstract records.

Now, there is some duplication of content here &#8211; the colors for Union blue and Confederate red have to be set separately in each of the three sets of abstract styling records. This is because all of the styles/visibilities on record can only be a part of a single inheritance chain, making it necessary to &#8220;split&#8221; each of the three chains under the top-level map records.

Originally, I toyed around with the idea of making it possible to create &#8220;style-specific&#8221; inheritance chains &#8211; so, for example, a record could inherit its fill color from one record, its line width from another, its visibility from another, etc. In the end, though, this would have required a large amount of added UI overhead, and the same results can be achieved with a minimal amount of extra work with the technique used here.

 [1]: http://neatline.org
 [2]: http://omeka.org
 [3]: http://hotchkiss.scholarslab.org/neatline-exhibits/show/battle-of-chancellorsville/fullscreen