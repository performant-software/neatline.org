---
title: Announcing Neatline 2.0.0! A stable, production-ready release
author: dm4fn
excerpt: '[Cross-posted from dclure.org] It&rsquo;s finished! Today we&rsquo;re excited to announce Neatline 2.0.0, a stable, production-ready release of the new codebase that can be used to upgrade existing installations. If you&rsquo;re starting fresh with a new project, just download the new version and install it like any other Omeka plugin. If you&rsquo;re upgrading from Neatline 1.x,&hellip;. <a href="http://www.scholarslab.org/announcements/neatline-2-0/">More.</a>'
layout: post
permalink: /2013/07/09/announcing-neatline-2-0-0-a-stable-production-ready-release/
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
  - 'http://www.scholarslab.org/announcements/neatline-2-0/#comments'
"wfw:commentRSS":
  - http://www.scholarslab.org/announcements/neatline-2-0/feed/
syndication_feed:
  - http://www.scholarslab.org/tag/neatline/feed
syndication_feed_id:
  - 8
syndication_permalink:
  - http://www.scholarslab.org/announcements/neatline-2-0/
syndication_item_hash:
  - 233a59acffdbe8b415d95c9ee6dbd230
  - 4767d0dc2b94ad061a01a081b5020325
categories:
  - Announcements
  - Geospatial and Temporal
  - neatline
---
<span class="Z3988" title="ctx_ver=Z39.88-2004&rft_val_fmt=info%3Aofi%2Ffmt%3Akev%3Amtx%3Adc&rfr_id=info%3Asid%2Focoins.info%3Agenerator&rft.type=&rft.format=text&rft.title=Announcing+Neatline+2.0.0%21+A+stable%2C+production-ready+release&rft.source=Scholars%26%23039%3B+Lab&rft.date=2013-07-09&rft.identifier=http%3A%2F%2Fwww.scholarslab.org%2Fannouncements%2Fneatline-2-0%2F&rft.language=English&rft.subject=Announcements&rft.subject=Geospatial+and+Temporal&rft.aulast=McClure&rft.aufirst=David"></span> 
*[Cross-posted from [dclure.org][1]]*

[<img src="http://dclure.org/wp-content/uploads/2013/06/neatline-21-1024x293.png" alt="neatline-2" width="640" height="183" class="alignnone size-large wp-image-2594" />][2]

It&#8217;s finished! Today we&#8217;re excited to announce [Neatline 2.0.0][3], a stable, production-ready release of the new codebase that can be used to upgrade existing installations. If you’re starting fresh with a new project, just download the new version and install it like any other Omeka plugin. If you&#8217;re upgrading from Neatline 1.x, be sure to read through the [2.0 migration guide][4] before getting started (**most important &#8211; the 2.0 migration runs as a &#8220;background process,&#8221; which means that there could be a 10-20 second lag before your old exhibits are visible under the &#8220;Neatline&#8221; tab**). Then, if you want to use the SIMILE Timeline widget and item-browser panel that were built into the first version of Neatline, download [NeatlineSimile][5] and [NeatlineWaypoints][6], the two new sub-plugins that integrate those features seamlessly into the Neatline core. For more information, check out the (all new!) [documentation][7], which walks through the installation process in detail.

Download the plugins: **[Neatline][3]** | **[NeatlineWaypoints][6]** | **[NeatlineSimile][5]**

Neatline 2.0 is a major update that significantly expands the scope of the project. Building on the core set of geospatial annotation tools from the first version, we&#8217;ve turned Neatline into a general-purpose visual annotation framework that can be used to create interactive displays of almost any type of two-dimensional material &#8211; maps, paintings, drawings, photographs, documents, and anything else that can be captured as an image. We&#8217;ve also made a series of changes to the user interface and code architecture that are designed to make Neatline more accessible for new users (college undergraduates working on class assignments) and, at the same time, more flexible for advanced users (professional scholars, journalists, and digital artists who want to use Neatline for complex projects).

Some of the highlights:

*   **[Improved performance and scalability][8]**, powered by a real-time spatial querying system that makes it possible to work with really large collections of records &#8211; as many as about 1,000,000 in a single exhibit;

*   **[A more sophisticated set of drawing tools][9]**, including the ability to import high-fidelity SVG documents created in programs like Adobe Illustrator or Inkscape and interactively drag them into position as geometry in Neatline exhibits;

*   **[An interactive, CSS-like stylesheet system][10]**, build directly into the editing environment, that makes it possible to quickly perform bulk updates on large collections of records using a simplified dialect of CSS;

*   **[A flexible user-permissions system][11]**, designed to make it easier to use Neatline for class assignments and workshops, that makes it possible to prevent users from modifying or deleting content they didn&#8217;t create;

*   **Expanded support for non-spatial base layers** that makes it possible to build exhibits on top of any web-accessible static image or non-spatial WMS layer &#8211; paintings, drawings, photographs, documents, etc.

*   **A more powerful theming system**, which makes it possible for designers to completely customize the appearance and interactivity of each individual Neatline exhibit. This makes it possible to host completely independent and thematically-distinct projects inside a single installation of Omeka.

*   **A total rewrite of the front-end JavaScript applications** (both the editing environment and the public-facing exhibit views) that provides a more minimalistic and responsive environment for creating and viewing exhibits;

*   **A new programming API and &#8220;sub-plugin&#8221; system** that makes it possible for developers to add custom functionality for specific projects &#8211; everything from simple user-interface widgets (sliders, legends, scrollers, forward-and-backward buttons, etc.) up to really extensive modifications that expand the core data model and add totally new interactions.

And much more! Over the course of the next week, leading up to our panel about Neatline at the [DH 2013][12] conference in Lincoln, Nebraska (&#8220;Circular Development: Neatline and the User/Developer Feedback Loop,&#8221; Wednesday at 10:30), we&#8217;re going to be fleshing out the new documentation and building a set of Neatline-2.0-powered projects designed to put the new feature set through its paces.

Also, watch this space later in the week for another code release &#8211; we&#8217;ve built an extension called NeatlineTexts that connects Neatline exhibits with word-level annotations in long-format documents, which makes it possible to use Neatline as a publication platform for essays, blog posts, scholarly articles, monographs, etc., and built a special Omeka that&#8217;s specifically designed to frame these interactive editions.

Until then &#8211; grab the new code, give it spin, and let us know what you think!

 [1]: http://dclure.org/?p=2577
 [2]: http://dclure.org/wp-content/uploads/2013/06/neatline-21.png
 [3]: http://omeka.org/add-ons/plugins/neatline/
 [4]: http://docs.neatline.org/upgrading-to-v2.html
 [5]: http://omeka.org/add-ons/plugins/neatlinesimile/
 [6]: http://omeka.org/add-ons/plugins/neatlinewaypoints/
 [7]: https://github.com/scholarslab/Neatline/wiki
 [8]: http://dclure.org/logs/neatline-one-million-records/
 [9]: http://dclure.org/logs/neatline-drawing-svg-on-maps/
 [10]: http://dclure.org/logs/interactive-css-in-neatline-2-0/
 [11]: http://dclure.org/logs/announcing-neatline-2-0-alpha2/
 [12]: http://dh2013.unl.edu/