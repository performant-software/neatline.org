---
title: Announcing Neatline 2.0.2!
author: dm4fn
excerpt: 'Today we&rsquo;re pleased to announce the release of Neatline 2.0.2! This is a maintenance release that adds a couple of minor features and fixes some bugs we&rsquo;ve rooted up in the last few weeks: Fixes a bug that was causing item-import queries to fail when certain combinations of other plugins were installed alongside Neatline (thanks&hellip;. <a href="http://www.scholarslab.org/geospatial-and-temporal/announcing-neatline-2-0-2/">More.</a>'
layout: post
permalink: /2013/08/07/announcing-neatline-2-0-2/
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
  - 'http://www.scholarslab.org/geospatial-and-temporal/announcing-neatline-2-0-2/#comments'
"wfw:commentRSS":
  - http://www.scholarslab.org/geospatial-and-temporal/announcing-neatline-2-0-2/feed/
syndication_feed:
  - http://www.scholarslab.org/tag/neatline/feed
syndication_feed_id:
  - 8
syndication_permalink:
  - http://www.scholarslab.org/geospatial-and-temporal/announcing-neatline-2-0-2/
syndication_item_hash:
  - b5b3b0b18c4106d90fb10061ad4e240c
  - 4884291b14ad2c27c265ba5ecd81edf3
categories:
  - Geospatial and Temporal
  - neatline
---
<span class="Z3988" title="ctx_ver=Z39.88-2004&rft_val_fmt=info%3Aofi%2Ffmt%3Akev%3Amtx%3Adc&rfr_id=info%3Asid%2Focoins.info%3Agenerator&rft.type=&rft.format=text&rft.title=Announcing+Neatline+2.0.2%21&rft.source=Scholars%26%23039%3B+Lab&rft.date=2013-08-07&rft.identifier=http%3A%2F%2Fwww.scholarslab.org%2Fgeospatial-and-temporal%2Fannouncing-neatline-2-0-2%2F&rft.language=English&rft.subject=Geospatial+and+Temporal&rft.aulast=McClure&rft.aufirst=David"></span> 
Today we&#8217;re pleased to announce the release of [**Neatline 2.0.2**][1]! This is a maintenance release that adds a couple of minor features and fixes some bugs we&#8217;ve rooted up in the last few weeks:

*   Fixes a bug that was causing item-import queries to fail when certain combinations of other plugins were installed alongside Neatline (thanks Jenifer Bartle and Trip Kirkpatrick for bringing this to our attention).

*   Makes it possible to toggle the real-time spatial querying on and off for each individual exhibit. This can be useful if you have a small exhibit (eg, 10-20 records) that can be loaded into the browser all at once without causing performance problems, and you want to avoid the added load on the server incurred by the dynamic querying.

*   Fixes some performance issues with the OpenStreetMap layer in Chrome.

And more! Check out the [release notes][2] for the full list of changes, and grab the new code from the [Omeka add-ons repository][1]. Also, watch this space for a couple of other Neatline-related releases in the coming weeks. Jeremy and I are working on a series of themes for Omeka specifically designed to display Neatline projects, including the NeatLight theme, which is currently used on the [Neatline Labs][3] site I&#8217;ve started playing around with (still a work in progress). We&#8217;re also just about ready to cut off a public release of the NeatlineText plugin, which makes it possible to connect records in Neatline exhibits to individual sections, paragraphs, sentences, and words in text documents (check out [this][4] example).

Until then, give the new code a spin, and let us know what you think!

 [1]: http://omeka.org/add-ons/plugins/Neatline/
 [2]: https://github.com/scholarslab/Neatline/releases/tag/2.0.2
 [3]: http://neatline.dclure.org/
 [4]: http://neatline.dclure.org/neatline/show/saturn-v-stage-2