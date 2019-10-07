---
title: Announcing Neatline 2.0-alpha1!
author: dm4fn
excerpt: '[Cross-posted with dclure.org] It&rsquo;s here! After much hard work, we&rsquo;re delighted to announce the first alpha release of Neatline 2.0, which migrates the codebase to Omeka 2.0 and adds lots of exciting new things. For now, this is just an initial testing release aimed at developers and other brave folks who want to tinker around&hellip;. <a href="http://www.scholarslab.org/geospatial-and-temporal/announcing-neatline-2-0-alpha1/">More.</a>'
layout: post
permalink: /2013/05/13/announcing-neatline-2-0-alpha1-2/
syndication_source:
  - 'Scholars&#039; Lab » neatline'
syndication_source_uri:
  - http://www.scholarslab.org
syndication_source_id:
  - http://www.scholarslab.org/tag/neatline/feed
"rss:comments":
  - 'http://www.scholarslab.org/geospatial-and-temporal/announcing-neatline-2-0-alpha1/#comments'
"wfw:commentRSS":
  - http://www.scholarslab.org/geospatial-and-temporal/announcing-neatline-2-0-alpha1/feed/
syndication_feed:
  - http://www.scholarslab.org/tag/neatline/feed
syndication_feed_id:
  - 8
syndication_permalink:
  - http://www.scholarslab.org/geospatial-and-temporal/announcing-neatline-2-0-alpha1/
syndication_item_hash:
  - cb9c71b6610a78c79c39e784af383855
  - e9ad74ec14fbbe32a65157b7e89bcdb9
  - a2b359483cbca6449c9859d0e98dc0b4
enclosure:
  - |
    |
        
        
        
categories:
  - Geospatial and Temporal
  - neatline
---
<span class="Z3988" title="ctx_ver=Z39.88-2004&rft_val_fmt=info%3Aofi%2Ffmt%3Akev%3Amtx%3Adc&rfr_id=info%3Asid%2Focoins.info%3Agenerator&rft.type=&rft.format=text&rft.title=Announcing+Neatline+2.0-alpha1%21&rft.source=Scholars%26%23039%3B+Lab&rft.date=2013-05-13&rft.identifier=http%3A%2F%2Fwww.scholarslab.org%2Fgeospatial-and-temporal%2Fannouncing-neatline-2-0-alpha1%2F&rft.language=English&rft.subject=Geospatial+and+Temporal&rft.aulast=McClure&rft.aufirst=David"></span> 
<img src="http://www.scholarslab.org/wp-content/uploads/2013/05/neatline-2.0-alpha1-small.png" alt="neatline-2.0-alpha1-small" width="600" height="153" class="alignnone size-full wp-image-8265" />

*[Cross-posted with [dclure.org][1]]*

It&#8217;s here! After much hard work, we&#8217;re delighted to announce the first alpha release of Neatline 2.0, which migrates the codebase to Omeka 2.0 and adds lots of exciting new things. For now, this is just an initial testing release aimed at developers and other brave folks who want to tinker around with the new set of features and help us work out the kinks. **Notably, this build doesn&#8217;t yet include the migration to upgrade existing exhibits from the 1.1.x series**, which we&#8217;ll ship with the first stable release in the next couple weeks once we&#8217;ve had a chance to field test the new code.

  
<small>45 minutes of Neatline 2.0 alpha testing, compressed to 90 seconds, set to Chopin.</small>

In the interest of modularity (more on this later), the set of features that was bundled together in the original version of Neatline has been split into three separate plugins:

*   **[Neatline][2]** &#8211; The core map-making toolkit and content management system.
*   **[NeatlineWaypoints][3]** &#8211; A list of sortable waypoints, the new version of the vertical &#8220;Item Browser&#8221; panel from the 1.x series.
*   **[NeatlineSimile][4]** &#8211; The SIMILE Timeline widget.

Just unpack the `.zip` archives, copy the folders into the `/plugins` directory in your Omeka 2.x installation, and install the plugins in the Omeka admin. For more detailed information, head over to the [**Neatline 2.0-alpha1 Installation Wiki**][5], and take a look at the [**change log**][6] for a more complete list of changes and additions.

We&#8217;re really excited about this code. Since releasing the first version last summer, we&#8217;ve gotten a huge amount of incredibly helpful feedback from users, much of which has been directly incorporated into the new release. We&#8217;ve also added a carefully-selected set of new features that opens up the door to some really interesting new approaches to geospatial (and completely *non*-geospatial) annotation. It&#8217;s a leaner, faster, more focused, more reliable, and generally more capable piece of software &#8211; we&#8217;re excited to start building projects with it!

Some of the additions and changes:

*   **Real-time spatial querying**, which makes it possible to create *really* large exhibits &#8211; as many as about 1,000,000 records on a single map;

*   **A total rewrite of the front-end application** in [Backbone.js][7] and [Marionette][8] that provides a more minimal, streamlined, and responsive environment for creating and publishing exhibits;

*   **An interactive &#8220;stylesheet&#8221; system** (inspired by projects like Mike Migurski&#8217;s [Cascadenick][9]), that makes it possible to use a dialect of CSS &#8211; built directly into the editing environment &#8211; to synchronize large batches of records;

*   **The ability to import high-fidelity SVG illustrations** created in specialized vector editing tools like Adobe Illustrator and Inkscape;

*   **The ability to add custom base layers**, which, among other things, makes it possible to annotate completely non-spatial entities &#8211; paintings, photographs, documents, and anything else that can be captured as an image;

*   **A revamped import-from-Omeka workflow** that makes it easier to link Neatline records to Omeka items and batch-import large collections of items;

*   **A flexible programming API and &#8220;sub-plugin&#8221; system** that makes it easy for developers to extend the core feature set with custom functionality for specific projects &#8211; everything from simple JavaScript widgets (legends, sliders, scrollers, etc.) up to really deep modifications that extend the core data model and add completely new interactions.

Over the course of the next two weeks, I&#8217;ll be writing in much more detail about some of the new features. In the meantime &#8211; let us know what you think! We&#8217;re going to be pushing out a series of alpha releases in pretty rapid succession over the course of the next couple weeks, and we&#8217;re really keen to get feedback about the new features before cutting off a stable 2.0 release. If you find a bug, or think of a feature that you&#8217;d like to see included, be sure to file a report on the [issue tracker][10].

 [1]: http://dclure.org/logs/announcing-neatline-2-0-alpha1/
 [2]: http://localhost:8888/neatline_wp/wp-content/uploads/2013/05/Neatline-2.0-alpha1.zip
 [3]: http://localhost:8888/neatline_wp/wp-content/uploads/2013/05/NeatlineWaypoints-0.1.zip
 [4]: http://localhost:8888/neatline_wp/wp-content/uploads/2013/05/NeatlineSimile-0.1.zip
 [5]: https://github.com/scholarslab/Neatline/wiki/Neatline-2.0-alpha1-Installation
 [6]: https://github.com/scholarslab/Neatline/blob/develop/CHANGELOG.md
 [7]: http://backbonejs.org/
 [8]: http://marionettejs.com/
 [9]: https://github.com/mapnik/Cascadenik
 [10]: https://github.com/scholarslab/Neatline/issues