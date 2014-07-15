---
title: Neatline 1.1.3 Maintenance Release
author: dm4fn
excerpt: 'This morning, Kiyonori Nagasaki noticed that one of the remote API&rsquo;s used by the Neatline 1.x releases went offline, which had the effect of breaking exhibits that included the SIMILE Timeline widget. To fix this, we just posted a 1.1.3 maintenance release that patches up the timeline problem and also includes a couple of other&hellip;. <a href="http://www.scholarslab.org/geospatial-and-temporal/neatline-1-1-3-maintenance-release/">More.</a>'
layout: post
permalink: /2013/05/16/neatline-1-1-3-maintenance-release-2/
syndication_source:
  - 'Scholars&#039; Lab » neatline'
syndication_source_uri:
  - http://www.scholarslab.org
syndication_source_id:
  - http://www.scholarslab.org/tag/neatline/feed
"rss:comments":
  - 'http://www.scholarslab.org/geospatial-and-temporal/neatline-1-1-3-maintenance-release/#comments'
"wfw:commentRSS":
  - http://www.scholarslab.org/geospatial-and-temporal/neatline-1-1-3-maintenance-release/feed/
syndication_feed:
  - http://www.scholarslab.org/tag/neatline/feed
syndication_feed_id:
  - 8
syndication_permalink:
  - http://www.scholarslab.org/geospatial-and-temporal/neatline-1-1-3-maintenance-release/
syndication_item_hash:
  - 1f88a77d0e1a0b8ffb6f9ef14db01f2f
  - 988220d61914254c2d11f6d749754398
  - 5f0afa9c1c1ed77e6c07868d436bfdcb
enclosure:
  - |
    |
        
        
        
categories:
  - Geospatial and Temporal
  - neatline
---
<span class="Z3988" title="ctx_ver=Z39.88-2004&rft_val_fmt=info%3Aofi%2Ffmt%3Akev%3Amtx%3Adc&rfr_id=info%3Asid%2Focoins.info%3Agenerator&rft.type=&rft.format=text&rft.title=Neatline+1.1.3+Maintenance+Release&rft.source=Scholars%26%23039%3B+Lab&rft.date=2013-05-16&rft.identifier=http%3A%2F%2Fwww.scholarslab.org%2Fgeospatial-and-temporal%2Fneatline-1-1-3-maintenance-release%2F&rft.language=English&rft.subject=Geospatial+and+Temporal&rft.aulast=McClure&rft.aufirst=David"></span> 
This morning, [Kiyonori Nagasaki][1] noticed that one of the remote API&#8217;s used by the Neatline 1.x releases went offline, which had the effect of breaking exhibits that included the SIMILE Timeline widget. To fix this, we just posted a [**1.1.3 maintenance release**][2] that patches up the timeline problem and also includes a couple of other improvements:

*   Disabled animated opacity transitions on WMS tiles, which were causing performance problems in recent builds of Chrome;

*   Fixed a bug that was causing the map not to focus correctly when a record is selected that has a default focus position/zoom, but no vector geometry.

[**Download Neatline 1.1.3**][2].

Meanwhile, lots of activity on the Neatline 2.0 front &#8211; we&#8217;re almost done with a second alpha release, which gets us one step closer to a stable 2.0 release, which will include the migration to update existing installations from the 1.x series.

Stay posted!

 [1]: https://twitter.com/knagasaki
 [2]: http://omeka.org/add-ons/plugins/neatline/