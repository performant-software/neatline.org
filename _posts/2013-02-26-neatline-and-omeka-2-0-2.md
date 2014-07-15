---
title: Neatline and Omeka 2.0
author: dm4fn
excerpt: '[Cross-posted with dclure.org] We&rsquo;ve been getting a lot of questions about when Neatline plugins will be ready for the newly-released Omeka 2.0. The answer is &ndash; very soon! In addition to migrating all of the plugins (Neatline, Neatline Time, Neatline Maps, Neatline Features) over to the new version of Omeka, we&rsquo;re also using this transition&hellip;. <a href="http://www.scholarslab.org/research-and-development/neatline-and-omeka-2/">More.</a>'
layout: post
permalink: /2013/02/26/neatline-and-omeka-2-0-2/
syndication_source:
  - 'Scholars&#039; Lab » neatline'
syndication_source_uri:
  - http://www.scholarslab.org
syndication_source_id:
  - http://www.scholarslab.org/tag/neatline/feed
"rss:comments":
  - 'http://www.scholarslab.org/research-and-development/neatline-and-omeka-2/#comments'
"wfw:commentRSS":
  - http://www.scholarslab.org/research-and-development/neatline-and-omeka-2/feed/
syndication_feed:
  - http://www.scholarslab.org/tag/neatline/feed
syndication_feed_id:
  - 8
syndication_permalink:
  - http://www.scholarslab.org/research-and-development/neatline-and-omeka-2/
syndication_item_hash:
  - 3ef4bccd68f36d93ad0959b2115583ea
  - c188c4e144aaf10cf470dd67ccf95364
  - aa922c817ed587013497f60593046e4c
enclosure:
  - |
    |
        
        
        
categories:
  - neatline
  - omeka
  - Research and Development
---
<span class="Z3988" title="ctx_ver=Z39.88-2004&rft_val_fmt=info%3Aofi%2Ffmt%3Akev%3Amtx%3Adc&rfr_id=info%3Asid%2Focoins.info%3Agenerator&rft.type=&rft.format=text&rft.title=Neatline+and+Omeka+2.0&rft.source=Scholars%26%23039%3B+Lab&rft.date=2013-02-26&rft.identifier=http%3A%2F%2Fwww.scholarslab.org%2Fresearch-and-development%2Fneatline-and-omeka-2%2F&rft.language=English&rft.subject=Research+and+Development&rft.aulast=McClure&rft.aufirst=David"></span> 
![null][1]

*[Cross-posted with [dclure.org][2]]*

We&#8217;ve been getting a lot of questions about when Neatline plugins will be ready for the [newly-released Omeka 2.0][3]. The answer is &#8211; very soon! In addition to migrating all of the plugins ([Neatline][4], [Neatline Time][5], [Neatline Maps][6], [Neatline Features][7]) over to the new version of Omeka, we&#8217;re also using this transition to roll out a major evolution of the Neatline feature-set that incorporates lots of feedback from the first version.

Some of the new, Omeka-2.0-powered things on tap:

*   [Real-time spatial querying on the map][8], which makes it possible to work with really large collections of data (as many as 1,000,000 records in a single exhibit);

*   The ability to [import SVG documents from vector-editing programs like Adobe Illustrator][9], making it possible to render complex illustrations on the map;

*   A portable stylesheet system that allows exhibit-builders to use a CSS-like syntax to apply bulk updates to large collections of records;

*   An improved workflow for displaying Omeka items in Neatline exhibits &#8211; mix and match individual Dublin Core fields, entire metadata records, images, and other item attributes;

*   A flexible workflow for adding custom base layers in exhibits, which makes it possible to use Neatline to annotate non-spatial materials: paintings, drawings, abstract maps, and anything else that can be captured as an image.

*   A new set of hooks and filters &#8211; both on the server and in the browser &#8211; that make it easy to for developers to write modular add-ons and customizations for Neatline exhibits &#8211; legends, sliders, record display formats, integrations with long-format texts, etc.

The new version is just about feature-complete, and we&#8217;re now in the process of tying up loose ends and writing the migration code to upgrade projects built on the 1.1.x releases. We&#8217;re on schedule for a public beta by the end of March, and a full release by the end of the semester.

Going forward, we&#8217;ll continue supporting the Omeka 1.5.x-compatible releases of Neatline from a maintenance standpoint, but we&#8217;re moving all new development efforts into the new versions of the plugins, which only work with Omeka 2.0.

As the final pieces fall into place over the course of the next couple weeks, we&#8217;ll start posting a series of alpha releases for developers and other folks who want to test-drive the new feature set. Between now and then, check out some of the feature-preview articles we&#8217;ve posted in the last couple weeks:

**[Neatline Feature Preview – 1,000,000 records in an exhibit][8]**  
**[Neatline Feature Preview – Importing SVG documents from Adobe Illustrator][9]** </ul> 
And watch this space for ongoing weekly updates!

 [1]: http://neatline.org/wp-content/themes/neatline-wp-theme/images/neatline-logo-rgb.png.pagespeed.ce.KWm9TWbLus.png
 [2]: http://dclure.org/logs/neatline-and-omeka-2
 [3]: http://omeka.org/blog/2013/01/24/omeka-2-0-drops-today/
 [4]: http://neatline.org/plugins/neatline/
 [5]: http://neatline.org/plugins/neatline-time/
 [6]: http://neatline.org/plugins/neatline-maps/
 [7]: http://neatline.org/plugins/neatline-features/
 [8]: http://dclure.org/logs/neatline-one-million-records/
 [9]: http://dclure.org/logs/neatline-drawing-svg-on-maps/