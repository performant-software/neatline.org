---
title: Neatline 1.1.3 Maintenance Release
author: clured
layout: post
permalink: /2013/05/28/neatline-1-1-3-maintenance-release/
categories:
  - Releases
---
This morning, [Kiyonori Nagasaki][1] noticed that one of the remote API&#8217;s used by the Neatline 1.x releases went offline, which had the effect of breaking exhibits that included the SIMILE Timeline widget. To fix this, we just posted a [**1.1.3 maintenance release**][2] that patches up the timeline problem and also includes a couple of other improvements:

*   Disabled animated opacity transitions on WMS tiles, which were causing performance problems in recent builds of Chrome;

*   Fixed a bug that was causing the map not to focus correctly when a record is selected that has a default focus position/zoom, but no vector geometry.

[**Download Neatline 1.1.3**][2].

Meanwhile, lots of activity on the Neatline 2.0 front &#8211; we&#8217;re almost done with a second alpha release, which gets us one step closer to a stable 2.0 release, which will include the migration to update existing installations from the 1.x series.

Stay posted!

 [1]: https://twitter.com/knagasaki
 [2]: http://omeka.org/add-ons/plugins/neatline/