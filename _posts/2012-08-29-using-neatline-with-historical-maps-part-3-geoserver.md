---
title: 'Using Neatline with historical maps :: Part 3 &#8211; GeoServer'
author: clured
layout: post
permalink: /2012/08/29/using-neatline-with-historical-maps-part-3-geoserver/
categories:
  - Tutorials
---
*[Cross-posted with <a href="http://dclure.org/tutorials/neatline-maps-geoserver/" target="_blank">dclure.org</a> and <a href="http://www.scholarslab.org/geospatial-and-temporal/using-neatline-with-historical-maps-geoserver/" target="_blank">scholarslab.org</a>]*

<small><em>This is part 3 of a 3-post tutorial that walks through process of georeferencing a historical map and using it in GeoServer and Neatline.</em></small>

In [part 1][1] of this series, we used ArcMap to convert a static image into a georeferenced .tiff file. In [part 2][2], we post-processed the file with `gdal` to remove the black borders around the image. In this article, we&#8217;ll load the .tiff file into GeoServer and import the final web map service into a Neatline exhibit.

**Generating the web map service on GeoServer**

There are two ways to upload the .tiff file to GeoServer &#8211; the entire process can be performed through the Omeka interface using the Neatline Maps plugin, or the file can be uploaded directly onto the machine running GeoServer and the service created by way of the GeoServer administrative interface.

The first option is easier, but there&#8217;s a fundamental restriction that makes it unworkable in certain situations &#8211; since Neatline Maps has to upload the .tif file through Omeka before it can create the map service via the GeoServer API, it&#8217;s impossible to upload files through Neatline Maps that are larger than the file upload limit set by the [`upload_max_filesize`][3] and [`post_max_size`][4] settings in the php.ini file on your server.

Depending on the hosting environment, these values can be set to anywhere from 2-20 megabytes by default. If you have access to the php.ini file, you can bump up the limit, but beyond a certain point it probably makes more sense just to upload the file directly to the server running GeoServer and create the web services through GeoServer administrative interface. Since high-resolution .tiff files can easily weight in a hundreds of megabytes or even gigabytes, this is often a more controlled and reliable approach, especially in cases where you&#8217;re working with multiple files at once.

Regardless of how the file is uploaded, the final process of importing the map service into Omeka and Neatline works the same way.

**Option 1: Upload through Neatline Maps**

If your file is small enough to be uploaded through Omeka, the Neatline Maps plugin provides plug-and-play connectivity with GeoServer:

1.  With Neatline Maps installed, click on the &#8220;Neatline Maps&#8221; tab in the top toolbar of the Omeka administrative interface and click on &#8220;Create Server.&#8221; Fill in the URL, Username, and Password for your GeoServer. In the Name section, enter a plaintext identifier for the server (used for content management in Omeka) and use the Workspace field to specify the workspace on the GeoServer installation that will house the new stores and layers. Click &#8220;Save&#8221; to create the server record. 
    (**Note**: If you want to upload files to more than one installation of GeoServer, you can create as many server records as you want. At any given point, though, only one of the record can be marked as the &#8220;Active&#8221; server &#8211; this the server that the plugin will use to handle new .tif uploads).
    
    <a href="http://www.scholarslab.org/wp-content/uploads/2012/07/create-server.jpg" rel="attachment wp-att-5167"><img src="http://www.scholarslab.org/wp-content/uploads/2012/07/create-server-300x245.jpg" alt="" title="create-server" width="300" height="245" class="alignnone size-medium wp-image-5167" /></a>

2.  Create an item to associate the web map service with (or edit an existing item). In the Item add/edit form, click on the &#8220;Files&#8221; tab, click on &#8220;Choose File,&#8221; and select the .tiff file as you would for a regular file upload. When you save the item, Neatline Maps will automatically detect that you&#8217;re trying to upload a georeferenced .tif file and create a corresponding web map service by way of the GeoServer API. 
    <a href="http://www.scholarslab.org/wp-content/uploads/2012/07/upload-file.jpg" rel="attachment wp-att-5170"><img src="http://www.scholarslab.org/wp-content/uploads/2012/07/upload-file-300x124.jpg" alt="" title="upload-file" width="300" height="124" class="alignnone size-medium wp-image-5170" /></a>
    
    Once you&#8217;ve saved the file, if you go back into the Item edit form and click on the &#8220;Web Map Service&#8221; tab, you&#8217;ll notice that &#8220;WMS Address&#8221; and &#8220;Layers&#8221; fields have been automatically updated to point to the new web map service. On the show page for the item, the map will be displayed in a small, interactive widget below the default metadata fields.</li> </ol> 
    **Option 2: Upload directly to GeoServer**
    
    1.  First, upload the file to the server running GeoServer with `scp` or another file transfer protocol. It&#8217;s usually a good idea to get the file out of the `/tmp` directory, but it doesn&#8217;t matter beyond that &#8211; GeoServer can read the entire file system. We&#8217;ve gotten into the habit of putting the source .tiff files in `/var/geotiff`.
    
    2.  In the GeoServer administrative interface, click on &#8220;Stores&#8221; in the left column and then click &#8220;Add new Store.&#8221; On the next screen, click GeoTIFF under the &#8220;Raster Data Sources&#8221; heading.
        
        <a href="http://www.scholarslab.org/wp-content/uploads/2012/07/new-data-store.jpg" rel="attachment wp-att-5175"><img src="http://www.scholarslab.org/wp-content/uploads/2012/07/new-data-store-300x159.jpg" alt="" title="new-data-store" width="300" height="159" class="alignnone size-medium wp-image-5175" /></a>
    
    3.  Select a workspace for the store and enter a name. Under &#8220;Connection Parameters,&#8221; click the &#8220;Browse..&#8221; link, and use the pop-up window to navigate to the file. Click &#8220;Save&#8221; to create the store.
        
        <a href="http://www.scholarslab.org/wp-content/uploads/2012/07/connection-parameters.jpg" rel="attachment wp-att-5178"><img src="http://www.scholarslab.org/wp-content/uploads/2012/07/connection-parameters-300x162.jpg" alt="" title="connection-parameters" width="300" height="162" class="alignnone size-medium wp-image-5178" /></a>
    
    4.  Next, we have to publish the store as a public-facing layer. On the next screen, click the &#8220;Publish&#8221; link.
        
        <a href="http://www.scholarslab.org/wp-content/uploads/2012/07/publish.jpg" rel="attachment wp-att-5181"><img src="http://www.scholarslab.org/wp-content/uploads/2012/07/publish-300x158.jpg" alt="" title="publish" width="300" height="158" class="alignnone size-medium wp-image-5181" /></a>
    
    5.  Now, the tricky part. We have to manually tell GeoServer to deliver the layer using a coordinate projection system that Neatline can use to layer the map on top of the real-geography base layers in OpenLayers. Scroll down to the &#8220;Coordinate Reference Systems&#8221; heading and enter `EPSG:900913` into the &#8220;Declared SRS&#8221; field. Under &#8220;SRS handling,&#8221; select &#8220;Force declared.&#8221; Under the &#8220;Bounding Boxes&#8221; heading, click both the &#8220;Compute from data&#8221; and &#8220;Compute from native bound&#8221; links.
        
        <a href="http://www.scholarslab.org/wp-content/uploads/2012/07/coordinates.jpg" rel="attachment wp-att-5184"><img src="http://www.scholarslab.org/wp-content/uploads/2012/07/coordinates-274x300.jpg" alt="" title="coordinates" width="274" height="300" class="alignnone size-medium wp-image-5184" /></a>
    
    Now, with the layer created, we can associate the new web map service with an item in your Omeka collection by manually filling in the two fields in the &#8220;Web Map Services&#8221; tab:
    
    1.  Go back the Omeka administrative interface and find the item that you want to associate the map with (or just create a new item). Open up the edit form for the item.</li> 
        *   Click the &#8220;Web Map Services&#8221; tab. Fill in the the top-level WMS address for the GeoServer installation (this always ends with `/wms`, and might look something like `localhost:8080/GeoServer/wms`) and enter the list of comma-delimited layers that you want to be associated with the item. For example, if you have a workspace called &#8220;hotchkiss&#8221; with layers &#8220;chancellorsville&#8221; and &#8220;fredericksburg,&#8221; you could enter:
            
            `hotchkiss:chancellorsville,hotchkiss:fredericksburg`.
            
            <a href="http://www.scholarslab.org/wp-content/uploads/2012/07/wms-tab.jpg" rel="attachment wp-att-5189"><img src="http://www.scholarslab.org/wp-content/uploads/2012/07/wms-tab-300x181.jpg" alt="" title="wms-tab" width="300" height="181" class="alignnone size-medium wp-image-5189" /></a>
        
        *   Save the item.</ol> 
        
        **Use the map in a Neatline exhibit**
        
        The two methods both have the end result of filling in the two fields in the &#8220;Web Map Services&#8221; tab. The only difference is in whether the .tif file is uploaded through Omeka or directly into GeoServer.
        
        Once an item is linked to a web map service, Neatline automatically detects the map and loads it into an exhibit when the item is activated on the map. With the item queried into the editing environment for an exhibit, just check the middle of the three checkboxes next to the listing for the item in the content management panel:
        
        [<img src="http://www.scholarslab.org/wp-content/uploads/2012/08/map-activation-300x178.jpg" alt="" title="map-activation" width="300" height="178" class="alignnone size-medium wp-image-5780" />][5]
        
        &#8230;and the WMS layer will appear on the map:
        
        [<img src="http://www.scholarslab.org/wp-content/uploads/2012/08/map-in-exhibit-300x195.jpg" alt="" title="map-in-exhibit" width="300" height="195" class="alignnone size-medium wp-image-5781" />][6]

 [1]: http://neatline.org/2012/08/20/using-neatline-with-historical-maps-part-1-georeferencing/
 [2]: http://neatline.org/2012/08/23/using-neatline-with-historical-maps-part-2-transparency/
 [3]: http://www.php.net/manual/en/ini.core.php#ini.upload-max-filesize
 [4]: http://www.php.net/manual/en/ini.core.php#ini.post-max-size
 [5]: http://www.scholarslab.org/wp-content/uploads/2012/08/map-activation.jpg
 [6]: http://www.scholarslab.org/wp-content/uploads/2012/08/map-in-exhibit.jpg