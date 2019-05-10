---
title: 'Using Neatline with historical maps :: Part 1 &#8211; Georeferencing'
author: clured
layout: post
permalink: /2012/08/20/using-neatline-with-historical-maps-part-1-georeferencing/
categories:
  - Tutorials
---
*[Cross-posted with <a href="http://www.scholarslab.org/geospatial-and-temporal/using-neatline-with-historical-maps-georeferencing/" target="_blank">scholarslab.org</a>]*

Out of the box, <a href="http://neatline.org/" target="_blank">Neatline</a> (our recently-released framework for building geotemporal exhibits) can be used to create geo-temporal exhibits based on &#8220;modern-geography&#8221; base-layers &#8211; OpenStreetMap, Google satellite and street maps, and a collection of beautiful, stylized layers from Stamen Design. For historical and literary projects, though, one of Neatline&#8217;s most powerful features is its deep integration with Geoserver, an open-source geospatial server that can pipe georeferenced historical maps directly into Neatline exhibits. For some examples of this, [check][1] [out][2] [these][3] [four][4] demo exhibits built on Civil War battle maps by Jedediah Hotchkiss.

Geoserver is a pretty complex piece of software, and the process of assigning geographic coordinates to static image files (called &#8220;georeferencing&#8221; or &#8220;georectifying&#8221;) can be a bit tricky at first. This is the first post in a three-part series that will walk through the entire process of rectifying a historical map using ArcMap, post-processing the image, uploading it to Geoserver, and importing the final web map service into a Neatline exhibit.

**Georectification**

To start, all you need is a static image file that can be positioned in some way or another on top of a real-geography base layer. Usually, this is a map of some sort, but it could also be aerial photography, or, in more experimental and interpretive use-cases, it could even be a totally non-geographic image that would gain some kind of meaning from being situated in a geospatial context (for example, see the georeferenced manuscript pages in the &#8220;[My Dear Little Nelly][1]&#8221; exhibit).

Since the final map will be presented in an interactive environment that lets the user zoom in and out at will, it&#8217;s best to try to find a high-resolution version of the image you want to work with, which will make it possible to zoom further in before the image starts to noticeably pixelate. That said, the images don&#8217;t need to be excessively large &#8211; as Kelly Johnston (one of the GIS specialists in the Scholars&#8217; Lab) pointed out, *extremely* high-fidelity images (~10,000 pixels in height or width) often don&#8217;t really provide that much more value than somewhat smaller images, and can have the effect of choking up Geoserver and slowing down the speed with which the map is rendered in the final Neatline exhibit. For historical and literary use cases, I&#8217;ve found that images with dimensions in the 3000-5000 pixel range provide a good balance of resolution and speed.

In this tutorial, I&#8217;ll be working with map #124 in the [Hotchkiss Map Collection][5] at the Library of Congress (see the full list of maps [here][6]). To get the static image file, go to the [view page for the map][7] and right click on the &#8220;Download JPEG2000 image&#8221; link at the bottom of the screen and click &#8220;Save Link As&#8230;&#8221;

With the image in hand, let&#8217;s fire up ArcMap and get the environment set up:

1.  **Add a base map** by clicking on `File > Add Data > Add Basemap`. The base map is the real-geography foundation, the &#8220;true&#8221; map against which the image will be referenced. Select one of the nine options and click &#8220;Add.&#8221; This is largely just a matter of preference. For for maps with a lot of human geography (roads, railroads, cities), I like the &#8220;Bing Maps Road&#8221; layer, and for maps with natural geography (rivers, mountains, coastlines) I like the &#8220;USA Topo Maps&#8221; layer. After you&#8217;ve added a base map, a listing the layer will appear in the &#8220;Table of Contents&#8221; column on the left, which lists out all of the assets available in the environment. You can toggle layers on and off by clicking the checkbox next to the layer title.
    
    <a href="http://static.scholarslab.org/wp-content/uploads/2012/07/base-layer.jpg" rel="attachment wp-att-5107"><img src="http://static.scholarslab.org/wp-content/uploads/2012/07/base-layer-300x240.jpg" alt="" title="base-layer" width="300" height="240" class="alignnone size-medium wp-image-5107" /></a>

2.  **Add the static image** that you want rectify by clicking on `File > Add Data > Add Data`. Navigate to the location of the image, select it, and click &#8220;Add.&#8221; (Note: If the folder containing the image is not already available in the dropdown menu to the right of &#8220;Look in,&#8221; you may have to &#8220;connect&#8221; to the folder by clicking on the folder icon with the black &#8220;+&#8221; symbol in the toolbar to the right. Select the folder, click &#8220;OK,&#8221; and the folder should become available in the main dropdown menu.) If you get a popup asking if you want to generate pyramids, click &#8220;No,&#8221; and if you get an alert labeled &#8220;Unknown Spatial Reference,&#8221; click &#8220;OK&#8221; (ArcMap is just reacting to the fact that the image doesn&#8217;t have existing geo-coordinates).
    
    <a href="http://static.scholarslab.org/wp-content/uploads/2012/07/add-data.jpg" rel="attachment wp-att-5106"><img src="http://static.scholarslab.org/wp-content/uploads/2012/07/add-data-300x207.jpg" alt="" title="add-data" width="300" height="207" class="alignnone size-medium wp-image-5106" /></a>

3.  **Enable the Georeferencing toolbar** by clicking `Customize > Toolbars > Georeferencing`. The toolbar will appear at the top of the screen, and can be merged into the main top bar by dragging it upwards in the direction of the main navigation controls.
    
    <a href="http://static.scholarslab.org/wp-content/uploads/2012/07/georeferencing-toolbar.jpg" rel="attachment wp-att-5110"><img src="http://static.scholarslab.org/wp-content/uploads/2012/07/georeferencing-toolbar-300x54.jpg" alt="" title="georeferencing-toolbar" width="300" height="54" class="alignnone size-medium wp-image-5110" /></a>

4.  **Move to the rough location of the image that&#8217;s being rectified** by using the navigation controls at the left of the top toolbar to zoom the base map to the approximate location and bounds of the historical map. In this example, since the image I&#8217;m working with shows the town of Fredericksburg and the course of the Rappahannock southeast of the town, I&#8217;ll center the viewport a bit below and left of Fredericksburg, maybe zoomed back a bit to show the whole area that will be covered by the image.
    
    <a href="http://static.scholarslab.org/wp-content/uploads/2012/07/initial-focus.jpg" rel="attachment wp-att-5111"><img src="http://static.scholarslab.org/wp-content/uploads/2012/07/initial-focus-300x203.jpg" alt="" title="initial-focus" width="300" height="203" class="alignnone size-medium wp-image-5111" /></a>

5.  **Show the static image** by clicking on `Georeferencing > Fit To Display`. This just plasters the map directly on top of the base layer, using the bounds of the current viewport (set in the first step) to determine the position and scale of the image. Basically, this is just setting a crude, starting starting set of geo-coordinates that can be refined by laying down point associations.
    
    <a href="http://static.scholarslab.org/wp-content/uploads/2012/07/fit-to-display.jpg" rel="attachment wp-att-5109"><img src="http://static.scholarslab.org/wp-content/uploads/2012/07/fit-to-display-300x204.jpg" alt="" title="fit-to-display" width="300" height="204" class="alignnone size-medium wp-image-5109" /></a>

Now, the actual rectification. All this entails is creating a series of associations (at least two, as many as ~15-20) between points on the static image and points on the real-geography base layer. As you add points, ArcMap will automatically pan, rotate, scale, and ultimately &#8220;warp&#8221; the image to match the underlying base layer.

1.  **Lay a positioning point**: I like to start by picking the most obvious, central, easy-to-find point on the historical map. In this case, I&#8217;ll use the position at which the Richmond Fredericksburg Railroad crosses over the west bank Rappahannock. To lay the first point, click on the &#8220;Add Control Points&#8221; button in the Georeferencing toolbar and click at the exact position on the historical map that you want to use as the starting point. Then, without clicking down on the map viewport again, move the cursor over to the &#8220;Table of Contents&#8221; pane and check off the historical map, leaving just the base layer visible. Then, click on the location on the base layer that corresponds to the original location on the historical map. 
    Once you&#8217;ve clicked for a second time, the dotted line between the two clicks will disappear. Display the historical map again by checking the box next to its title in the &#8220;Table of Contents.&#8221; The image will now be anchored onto the base layer around the location of the first point association.
    
    <a href="http://static.scholarslab.org/wp-content/uploads/2012/07/first-point.jpg" rel="attachment wp-att-5108"><img src="http://static.scholarslab.org/wp-content/uploads/2012/07/first-point-300x203.jpg" alt="" title="first-point" width="300" height="203" class="alignnone size-medium wp-image-5108" /></a>

2.  **Lay a scaling and rotation point**: Next, pick another easily-mappable point on the historical map, this time ideally near the edges of the image, or at least some significant distance from the first point. Follow the same steps of clicking on the historical map, hiding the historical map, clicking on the corresponding location on the base layer, and then re-enabling the historical map to see the effect. 
    <a href="http://static.scholarslab.org/wp-content/uploads/2012/07/second-point.jpg" rel="attachment wp-att-5113"><img src="http://static.scholarslab.org/wp-content/uploads/2012/07/second-point-300x204.jpg" alt="" title="second-point" width="300" height="204" class="alignnone size-medium wp-image-5113" /></a>

At this point, you already have a minimally rectified image &#8211; the second point will both scale the image down to roughly correct proportions and rotate the image to the correct orientation. From this point forward, adding more points will make the rectification increasingly accurate and granular by &#8220;warping&#8221; the image, like a sheet of rubber, to fit the lattice of points as accurately as possible.

How many points is enough? Really, it depends on the accuracy of the map and objectives of the Neatline exhibit. In this case, Hotchkiss&#8217; map is already quite accurate, and the just first two points do a pretty good job of orienting the map and showing how it fits into the larger geography of the region. For literary and historical projects that don&#8217;t gain anything from extreme precision, a handful of points (2-5) is often sufficient.

When a higher level of precision is required, though, or when the historial map is significantly inaccurate (as is the case for older maps), more points (10-20) can be necessary. It&#8217;s not an exact science &#8211; just lay points until it looks right.

As you work (especially in cases where you&#8217;re laying down a lot points) experiment with different &#8220;transformation&#8221; algorithms by clicking `Georeferencing > Transformations` and selecting one of the five options (1st Order Polynomial, 2nd Order Polynomial, etc). Behind the scenes, these algorithms represent different computational approaches to &#8220;fitting&#8221; the image based on the set of control points &#8211; some of the transformations will leave the image roughly polygonal, whereas others will dramatically &#8220;warp&#8221; the shape of the image to make it conform more accurately to the point associations. Depending on the type of image you&#8217;re working with and its accuracy relative to the base layer, different transformations will produce more or less pleasing results. For now, I&#8217;ll just leave it at 1st Order Polynomial.

Once you&#8217;re done laying points, save off the image as a georeferenced .tiff file by clicking `Georeferencing > Rectify`. As desired, change the filename and target directory, and click &#8220;Save.&#8221;

<a href="http://static.scholarslab.org/wp-content/uploads/2012/07/rectify.jpg" rel="attachment wp-att-5112"><img src="http://static.scholarslab.org/wp-content/uploads/2012/07/rectify-300x223.jpg" alt="" title="rectify" width="300" height="223" class="alignnone size-medium wp-image-5112" /></a>

**Links**

[ArcGIS georeferencing documentation][8]  
[Quantum GIS georeferencing tutorial][9] (open-source alternative to ArcMap)  
[Georeferencing &#8211; making historic maps spatial][10]

 [1]: http://hotchkiss.scholarslab.org/neatline-exhibits/show/my-dear-little-nelly/fullscreen
 [2]: http://hotchkiss.scholarslab.org/neatline-exhibits/show/battle-of-chancellorsville/fullscreen
 [3]: http://hotchkiss.neatline.org/neatline-exhibits/show/chancellorsville-may-2-1863-132/fullscreen
 [4]: http://hotchkiss.scholarslab.org/neatline-exhibits/show/chancellorsville-may-3-4-1863-138/fullscreen
 [5]: http://memory.loc.gov/ammem/collections/maps/hotchkiss/index.html
 [6]: http://memory.loc.gov/ammem/collections/maps/hotchkiss/hotchkisslist.pdf
 [7]: http://memory.loc.gov/cgi-bin/map_item.pl?data=/home/www/data/gmd/gmd388/g3884/g3884f/cwh00124.jp2&style=gmd&itemLink=r?ammem/gmd:@field(NUMBER+@band(g3884f+cwh00124))&title=[Map%20of%20Fredericksburg,%20Va.,%20and%20vicinity].
 [8]: http://help.arcgis.com/en/arcgisdesktop/10.0/help/index.html#//009t000000mn000000
 [9]: http://qgis.spatialthoughts.com/2012/02/tutorial-georeferencing-topo-sheets.html
 [10]: http://spatial.scholarslab.org/making-historic-maps-spatial-georeferencing/