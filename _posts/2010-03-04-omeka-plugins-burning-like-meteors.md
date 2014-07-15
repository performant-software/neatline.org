---
title: Omeka plugins burning like meteors
author: Adam Soroka
layout: post
permalink: /2010/03/04/omeka-plugins-burning-like-meteors/
categories:
  - Uncategorized
---
[As Adam Soroka described in his last post, we made a shift to [Omeka][1] early in the Neatline project in order to speed development and put our work in the hands of end users already thinking about the relationship of archival collections to scholarly analysis and presentation. Omeka's plugin architecture also allows us to share individual components of the project (such as EAD import or robust SIMILE Timeline integration) with people who might not be interested in the whole geospatial workflow of Neatline proper, and to capitalize on [other Omeka-related work][2] happening in the [Scholars' Lab][3]. Here, Adam gives a quick update on work in progress. In a future post I'll describe the kinds of iterative scholarly work and geo-temporal interpretive activity that Neatline is designed to promote. -- Bethany]

The Neatline technical crew is hurtling onwards in our Omeka [plugin rampage][2]. 

[Ethan Gruber][4] is now finishing work on his [EAD Importer][5]. This will allow folks to bring an [Encoded Archival Description][6] XML finding aid to an Omeka instance and have the documents in that archival description sprout right into the Omeka field as manipulable, annotate-able, curate-able items. We&#8217;ve successfully applied it to our two test cases (H.P. Lovecraft and Jedediah Hotchkiss) and are working through other examples.

I have been madly thrashing a geospatially-enabled duo of plugins: [Neatline Maps][7] and [Neatline Features][8]. Neatline Maps connects the powerful open-source Web GIS engine [GeoServer][9] to Omeka. It permits a user to upload [georeferenced][10] images and have them immediately available as interactive maps. Neatline Features allows users to use a simple but powerful graphical editor built on the [OpenLayers][11] library to attach sophisticated georeferenced shape information to Omeka items. This could include anything from an outline of a building to the path taken by an army brigade through a battle.

Lastly, we&#8217;ve [participated][12] in [CHNM][13]&#8216;s Omeka [plugin rush][14] and written a new [Timeline][15] plugin to replace an [obsolete design][16]. We hope to have it published within a few days.

We&#8217;re well on our way to our expected May public release. &#8212; Adam

 [1]: http://omeka.org/
 [2]: http://www.scholarslab.org/projects/omeka-plugins/
 [3]: http://lib.virginia.edu/scholarslab/
 [4]: http://www.scholarslab.org/contributors/ewg4x/
 [5]: https://addons.omeka.org/svn/plugins/EadImporter/trunk/
 [6]: http://www.loc.gov/ead/
 [7]: https://addons.omeka.org/svn/plugins/NeatlineMaps/trunk/
 [8]: https://addons.omeka.org/svn/plugins/NeatlineFeatures/trunk/
 [9]: http://geoserver.org/display/GEOS/Welcome
 [10]: http://www.gsd.harvard.edu/gis/manual/georeferencing/index.htm
 [11]: http://openlayers.org/
 [12]: http://omeka.org/c/index.php/Plugin_Rush_2010#Timeline_.281.1-1.0.29
 [13]: http://chnm.gmu.edu/
 [14]: http://omeka.org/blog/2010/02/18/plugin-rush-2010/
 [15]: http://www.simile-widgets.org/timeline/
 [16]: https://addons.omeka.org/svn/plugins/Timeline/trunk/