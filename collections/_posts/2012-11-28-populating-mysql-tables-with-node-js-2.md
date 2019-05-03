---
title: Populating MySQL tables with Node.js
author: dm4fn
excerpt: '[Cross-posted from dclure.org] Over the course of the last week or so, I&rsquo;ve been working on implementing &ldquo;as-needed&rdquo; spatial geometry loading for Neatline &ndash; the map queries for new data in real-time as the user pans and zooms on the map, just loading the geometries that fall inside the bounding box of the current viewport.&hellip;. <a href="http://www.scholarslab.org/research-and-development/populating-mysql-tables-with-node-js/">More.</a>'
layout: post
permalink: /2012/11/28/populating-mysql-tables-with-node-js-2/
syndication_source:
  - 'Scholars&#039; Lab » neatline'
syndication_source_uri:
  - http://www.scholarslab.org
syndication_source_id:
  - http://www.scholarslab.org/tag/neatline/feed
"rss:comments":
  - 'http://www.scholarslab.org/research-and-development/populating-mysql-tables-with-node-js/#comments'
"wfw:commentRSS":
  - http://www.scholarslab.org/research-and-development/populating-mysql-tables-with-node-js/feed/
syndication_feed:
  - http://www.scholarslab.org/tag/neatline/feed
syndication_feed_id:
  - 8
syndication_permalink:
  - http://www.scholarslab.org/research-and-development/populating-mysql-tables-with-node-js/
syndication_item_hash:
  - 1b2455b6dca032f3fbdc674602d815b6
  - 5dfa97b6fc0cd814d07d1feab46286c1
enclosure:
  - |
    |
        
        
        
categories:
  - mysql
  - neatline
  - node.js
  - omeka
  - Research and Development
---
*[Cross-posted from [dclure.org][1]]*

Over the course of the last week or so, I&#8217;ve been working on implementing &#8220;as-needed&#8221; spatial geometry loading for Neatline &#8211; the map queries for new data in real-time as the user pans and zooms on the map, just loading the geometries that fall inside the bounding box of the current viewport. Using the spatial analysis functions baked into MySQL, this makes it possible to build out exhibits with many hundreds of thousands of spatial records, provided that the content is organized (in terms of spatial distribution and min/max zoom thresholds) so that no more than a couple hundred records of visible at any given point. I needed a way to build out a *really* big exhibit to run the new code through its paces.

Originally, mostly just because I was lazy to write the SQL, I had been generating testing data using a temporary development controller that called out to a helper functions that actually created the exhibits / records. These actions were invoked by Rake tasks that just spawned off GET requests to the controller actions. This works fine for relatively small data sets, but once I started trying to insert more than about 10,000 rows the loop ran for so long that the request timed out and the process died (at least, I think this was the problem).

And, either way, this is just generally slow (all in PHP) and clunky (litters up the codebase). Instead, I decided to write a couple of little standalone scripts that would programmatically build out a big SQL insert and run it directly on the database. In the past, I might have done this with Python, but I remembered how difficult it was to get the Python <-> MySQL bindings working in the past and decided to try in with Node.

This turns out to be easy and performant. The basic gist, using the standard [node-mysql][2] package:



It&#8217;s inefficient to run a separate `INSERT` query for each row; better to clump them together into a single, massive query, which can be accomplished by stacking up a bunch of parentheticals after the `VALUES`:



This can build out a 500,000-record exhibit in about 10 seconds:

[<img src="http://www.scholarslab.org/wp-content/uploads/2012/11/neatline-big-exhibit.jpg" alt="" title="neatline-big-exhibit" width="986" height="338" class="alignnone size-full wp-image-6940" />][3]

Full code [here][4].

 [1]: http://dclure.org/logs/populating-mysql-tables-with-node-js/
 [2]: https://github.com/felixge/node-mysql
 [3]: http://www.scholarslab.org/wp-content/uploads/2012/11/neatline-big-exhibit.jpg
 [4]: https://github.com/scholarslab/Neatline/blob/f0b9bc8626177ac9a21d6f9e72ed4d8af033a3fe/.dev/insert.js