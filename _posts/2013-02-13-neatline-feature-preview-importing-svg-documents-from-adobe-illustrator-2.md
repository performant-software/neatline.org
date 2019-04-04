---
title: Neatline Feature Preview – Importing SVG documents from Adobe Illustrator
author: dm4fn
excerpt: '[Cross-posted with dclure.org] ;tldr &ndash; The new version of Neatline makes it possible to take SVG documents created in vector editing software like Adobe Illustrator and Inkscape and &ldquo;drag&rdquo; them directly onto the map, just like a regular polygon. This makes it possible to create really sophisticated illustrations that go far beyond the blocky, &ldquo;sharp-edge&rdquo;&hellip;. <a href="http://www.scholarslab.org/research-and-development/neatline-drawing-svg-on-maps/">More.</a>'
layout: post
permalink: /2013/02/13/neatline-feature-preview-importing-svg-documents-from-adobe-illustrator-2/
syndication_source:
  - 'Scholars&#039; Lab » neatline'
syndication_source_uri:
  - http://www.scholarslab.org
syndication_source_id:
  - http://www.scholarslab.org/tag/neatline/feed
"rss:comments":
  - 'http://www.scholarslab.org/research-and-development/neatline-drawing-svg-on-maps/#comments'
"wfw:commentRSS":
  - http://www.scholarslab.org/research-and-development/neatline-drawing-svg-on-maps/feed/
syndication_feed:
  - http://www.scholarslab.org/tag/neatline/feed
syndication_feed_id:
  - 8
syndication_permalink:
  - http://www.scholarslab.org/research-and-development/neatline-drawing-svg-on-maps/
syndication_item_hash:
  - 41c1acd453c19ee74acbee233034f914
  - 3db2f29bd7805a4b03ed765f035e7677
enclosure:
  - |
    |
        
        
        
categories:
  - neatline
  - omeka
  - Research and Development
  - svg
---
*[Cross-posted with [dclure.org][1]]*

**;tldr** &#8211; The new version of Neatline makes it possible to take SVG documents created in vector editing software like Adobe Illustrator and [Inkscape][2] and &#8220;drag&#8221; them directly onto the map, just like a regular polygon. This makes it possible to create really sophisticated illustrations that go far beyond the blocky, &#8220;sharp-edge&#8221; style that we usually associate with digital maps. Check out the screencast (and scroll down for screenshots):



The first version of Neatline implemented a pretty standard set of GIS controls for sketching vector geometry onto maps &#8211; points, lines, and polygons. It was easy to sketch out simple shapes, but more difficult to create really intricate, complex illustrations.

Really, this is a sort of ubiquitous problem with digital maps, which tend to be good at representing *points*, but bad at representing *curves*. Under the hood, shapes on digital maps are represented by a series of X/Y coordinate pairs, wrapped up into different geometry types that store information about how the points should be displayed. For example, in [Well-Known Text][3] &#8211; the serialization format used by databases like PostGIS and MySQL &#8211; a line is represented by `LINESTRING(1 2,3 4,5 6)`, a polygon by `POLYGON((1 2,3 4,5 6,1 2))`, and so on and so forth. At the end of the day, everything is just a series of hard-coded points, strung together to form shapes.

This low-level organization in the data tends to bubble up to the level of user interfaces in the form of map sketching tools that make it easy to draw **jagged** shapes but hard to draw **smooth** shapes. For example, in the first version of Neatline, drawing this is easy:

[<img src="http://dclure.org/wp-content/uploads/2013/02/polygon-300x300.jpg" alt="polygon" width="300" height="300" class="alignnone size-medium wp-image-1889" />][4]

But this is much harder:

[<img src="http://dclure.org/wp-content/uploads/2013/02/arrow-300x224.jpg" alt="arrow" width="300" height="224" class="alignnone size-medium wp-image-1891" />][5]

It&#8217;s still possible, but it&#8217;s time-consuming and brittle &#8211; if you change your mind later and want to adjust the curvature of the arrow, you have to manually reposition dozens of points. This especially frustrating since, in other domains, this is a well-understood problem with lots of high-quality solutions: Vector graphics editors like Adobe Illustrator, [Inkscape][2], and even in-browser tools like [svg-edit][6] make it easy to create smooth, complex vector-based geometries that can be serialized to a portable XML format called [SVG][7] (Scalable Vector Graphics).

In the upcoming release of Neatline, we&#8217;ve made it possible to take SVG markup created in any vector editing tool and place it directly onto the map. Just save off any vector graphic as a SVG document, open up the file in a text editor, and paste the raw markup into the Neatline editor. Then just drag out the shape to any position, dimension, and orientation on the map. Once the new geometry is in place, it behaves just like regular points and polygons added with the default controls &#8211; it can be styled and edited just like anything else on the map.

This also opens up a whole new front of high-fidelity text-based annotation on digital maps. Since vector editors can convert strings of text into SVG paths, this makes it possible to sketch out labels, snippets, or even little paragraphs of content directly onto the map itself.

[<img src="http://dclure.org/wp-content/uploads/2013/02/neatline-1024x600.jpg" alt="neatline" width="640" height="375" class="alignnone size-large wp-image-1878" />][8]

[<img src="http://dclure.org/wp-content/uploads/2013/02/neatline-closeup-1024x598.jpg" alt="neatline-closeup" width="640" height="373" class="alignnone size-large wp-image-1879" />][9]

[<img src="http://dclure.org/wp-content/uploads/2013/02/slab-1024x599.jpg" alt="slab" width="640" height="374" class="alignnone size-large wp-image-1875" />][10]

[<img src="http://dclure.org/wp-content/uploads/2013/02/at-1024x600.jpg" alt="at" width="640" height="375" class="alignnone size-large wp-image-1880" />][11]

[<img src="http://dclure.org/wp-content/uploads/2013/02/at-closeup-1024x597.jpg" alt="at-closeup" width="640" height="373" class="alignnone size-large wp-image-1887" />][12]

 [1]: k:%20http://dclure.org/logs/neatline-drawing-svg-on-maps
 [2]: http://inkscape.org/
 [3]: http://en.wikipedia.org/wiki/Well-known_text
 [4]: http://dclure.org/wp-content/uploads/2013/02/polygon.jpg
 [5]: http://dclure.org/wp-content/uploads/2013/02/arrow.jpg
 [6]: http://svg-edit.googlecode.com/svn/branches/2.6/editor/svg-editor.html
 [7]: http://en.wikipedia.org/wiki/SVG
 [8]: http://dclure.org/wp-content/uploads/2013/02/neatline.jpg
 [9]: http://dclure.org/wp-content/uploads/2013/02/neatline-closeup.jpg
 [10]: http://dclure.org/wp-content/uploads/2013/02/slab.jpg
 [11]: http://dclure.org/wp-content/uploads/2013/02/at.jpg
 [12]: http://dclure.org/wp-content/uploads/2013/02/at-closeup.jpg