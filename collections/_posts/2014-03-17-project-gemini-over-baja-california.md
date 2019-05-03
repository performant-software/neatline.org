---
title: Project Gemini over Baja California
author: dm4fn
excerpt: '[Cross-posted from dclure.org] Launch the Exhibit A couple weeks ago, somewhere in the middle of a long session of free-association link hopping on Wikipedia, I stumbled into a cluster of articles about Project Gemini, NASA&rsquo;s second manned spaceflight program. Gemini, I quickly discovered, produced some spectacular photographs &ndash; many of them pointed downward towards the&hellip;. <a href="http://www.scholarslab.org/geospatial-and-temporal/project-gemini-over-baja-california/">More.</a>'
layout: post
permalink: /2014/03/17/project-gemini-over-baja-california/
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
  - 'http://www.scholarslab.org/geospatial-and-temporal/project-gemini-over-baja-california/#comments'
"wfw:commentRSS":
  - http://www.scholarslab.org/geospatial-and-temporal/project-gemini-over-baja-california/feed/
syndication_feed:
  - http://www.scholarslab.org/tag/neatline/feed
syndication_feed_id:
  - 8
syndication_permalink:
  - http://www.scholarslab.org/geospatial-and-temporal/project-gemini-over-baja-california/
syndication_item_hash:
  - 5acc771cba922157742d1b1b8810b5d4
categories:
  - d3
  - Geospatial and Temporal
  - neatline
---
<span class="Z3988" title="ctx_ver=Z39.88-2004&rft_val_fmt=info%3Aofi%2Ffmt%3Akev%3Amtx%3Adc&rfr_id=info%3Asid%2Focoins.info%3Agenerator&rft.type=&rft.format=text&rft.title=Project+Gemini+over+Baja+California&rft.source=Scholars%26%23039%3B+Lab&rft.date=2014-03-17&rft.identifier=http%3A%2F%2Fwww.scholarslab.org%2Fgeospatial-and-temporal%2Fproject-gemini-over-baja-california%2F&rft.language=English&rft.subject=Geospatial+and+Temporal&rft.aulast=McClure&rft.aufirst=David"></span> 
*[Cross-posted from [dclure.org][1]]*

## [Launch the Exhibit][2]

[<img src="http://dclure.org/wp-content/uploads/2014/03/gemini-screenshot-1024x615.jpg" alt="gemini-screenshot" width="640" height="384" class="alignnone size-large wp-image-3754" />][2]

A couple weeks ago, somewhere in the middle of a long session of free-association link hopping on Wikipedia, I stumbled into a cluster of articles about [Project Gemini][3], NASA&#8217;s second manned spaceflight program. Gemini, I quickly discovered, produced some spectacular photographs &#8211; many of them pointed downward towards the surface of the earth, capturing a dizzying opposition between the intelligible scale of the foreground (the 20-foot capsule, 100-foot tethering cords, 6-foot human bodies floating in space) and the completely unintelligible scale of the massive geographic entities below (peninsulas, continents, oceans).

As I started to click through the pictures, I found myself reflexively alt-tabbing back and forth between Chrome and Google Earth to compare them with the modern satellite imagery of the same geographic locations. Which made me think &#8211; why not try to actually combine the two into a single environment? Over the course of the next few days, I sketched out a little Neatline exhibit that plasters two photographs of Baja California Sur &#8211; taken about a year apart on Gemini 5 (August 1965) and Gemini 11 (September 1966) &#8211; around the Mapbox satellite imagery of the peninsula. Instead of lining up the coastlines to make the images overlay accurately on top of the satellite tiles, I just plunked them down on the map off to the side at a scale and orientation that makes it easy to compare the two. (We&#8217;ve [played around with this before][4], and I like to think of it as faux &#8211; or just especially humanistic! &#8211; georectification.)

[<img src="http://dclure.org/wp-content/uploads/2014/03/faux-georectification-1024x616.jpg" alt="faux-georectification" width="640" height="385" class="alignnone size-large wp-image-3774" />][5]

Then, using the drawing tools in Neatline, I blocked in some simple annotations that visually wire up the two sets of imagery &#8211; outlines around the four islands along the eastern coast of the peninsula, and arrows between the different instantiations of La Paz and San José del Cabo. I also wanted to find a way to visually formalize the difference in perspective between the Gemini photographs (oblique, wide-angle, deliberate) and the Mapbox tiles (flat-on, uniform). Using Illustrator, I created a long, ruler-like vector shape to label the ~200-mile distance between La Paz and the approximate positon of the Gemini 5 capsule when the picture was taken, and then used the &#8220;Perspective Grid&#8221; tool to render the shape in three dimensions and place it on top of the Gemini photograph, as if the same shape were physically positioned in front of the lens. In Illustrator:

[<img src="http://dclure.org/wp-content/uploads/2014/03/200-miles-illustrator-1024x564.jpg" alt="200-miles-illustrator" width="640" height="352" class="alignnone size-large wp-image-3767" />][6]

And placed in the Neatline exhibit, first to match the shallow angle of the Gemini shot:

[<img src="http://dclure.org/wp-content/uploads/2014/03/200-miles-1024x619.jpg" alt="200-miles" width="640" height="386" class="alignnone size-large wp-image-3764" />][7]

And then to match the perpendicular angle of the Mapbox tiles:

[<img src="http://dclure.org/wp-content/uploads/2014/03/200-miles-mapbox-1024x602.jpg" alt="200-miles-mapbox" width="640" height="376" class="alignnone size-large wp-image-3788" />][8]

I was also fascinated by the surreal opposition in scale between the Agena Target Vehicle (an unmanned spacecraft used for docking practice in orbit) and Isla San José, which sits serenely in the dark blue of the Gulf of California hundreds of miles below, but occupies almost exactly the same amount of space in the photograph as the 7-foot boom antenna on the Agena. In the space between the two, I dragged out two little shapes that map the sizes of things onto recognizable objects &#8211; a 6-foot person in the foreground, Manhattan in the background:

[<img src="http://dclure.org/wp-content/uploads/2014/03/manhattan-person-1024x617.jpg" alt="manhattan-person" width="640" height="385" class="alignnone size-large wp-image-3762" />][9]

**Perspective and Perspectivelessness**

These images fascinate me because they roll together two types of imagery &#8211; both ubiquitous on the web &#8211; that are almost exact opposites of one another. On the one hand, you have regular pictures, taken by regular (non-astronaut) people. These photographs freeze into place one particular *perspective* on things. In a literal sense, the world recedes from the lens in three dimensions &#8211; walls, buildings, bridges, mountains, valleys, clouds. Close things are big, distant things are small. Some are in focus, others aren&#8217;t. And unlike other forms of art like painting, poetry, sculpture, or music, which can claim (overconfidently, maybe) to graft completely new material onto the world, photographs innovate at the level of *stance* and *viewpoint*, the newness of the perspective on things that already exist. It&#8217;s less about what they add, more about what they subtract in order to whittle the world down to one particular frame. Why that angle? Why that moment? Why *that*, and not anything else?

On the other hand you have spatial photography &#8211; the satellite imagery used in [Google Maps][10], [Mapbox][11], [Bing Maps][12], etc. &#8211; which is almost completely *perspectiveless*, in just about every sense of the word. The world becomes a flat, depthless plane, photographed from a distance at a perpendicular angle. Instead of trying to find interesting new ways to crop down the world, spatial tiles try to be comprehensive and standardized. Instead of showing one thing, in one way, at one moment in time, they try to show everything, in the exact same way, at the exact same moment &#8211; now. The companies that source and assemble the satellite imagery race to keep it as current as possible, right at the threshold of the present. Last year, Google announced that its satellite imagery had been [purged of all clouds][13]. No doubt this makes it more functional, but it also does away with those wispy, bright-white threads of cloud that used to hang over the rainforests in Peru and Brazil, which were lovely. What&#8217;s gained, of course, is the intoxicating grandeur of it all, the ability to hold in a single view a photograph of the entire world &#8211; which, if nothing else, is some sort of crazy affirmation of human willpower. I always imagine Whitman, scratching out &#8220;[Salut au Monde][14]&#8220;, panning around Google Maps for inspiration.

Photographs taken by astronauts, though, collapse the distinction in interesting ways. They&#8217;re literally &#8220;satellite&#8221; photography, but they&#8217;re also drenched in subjectivity and historical stance. The oceans and continents spread out hundreds of miles below, just like on Google Maps or Mapbox &#8211; but the pictures were snapped with regular cameras by the hands of actual people, stuffed into little canisters falling around the world at thousands of miles an hour, which were only up there in the first place due to a crazy mix of socio-political ambitions and anxieties that were deeply characteristic of that particular moment in history. The Gemini imagery is haloed with little bits of space-race technology that instantly historicizes the frame &#8211; the nose cone of the capsule blocks out a huge swath of desert and ocean, the Agena vehicle hangs just a couple of hundred feet from the camera, tethered by a slight, ribbon-like cord that twists for hundreds of miles across the Gulf of California.

 [1]: http://dclure.org/logs/project-gemini-over-baja-california/
 [2]: http://neatline.dclure.org/neatline/show/gemini-over-baja-california
 [3]: http://en.wikipedia.org/wiki/Project_Gemini
 [4]: http://hotchkiss.neatline.org/neatline-exhibits/show/my-dear-little-nelly/fullscreen
 [5]: http://dclure.org/wp-content/uploads/2014/03/faux-georectification.jpg
 [6]: http://dclure.org/wp-content/uploads/2014/03/200-miles-illustrator.jpg
 [7]: http://dclure.org/wp-content/uploads/2014/03/200-miles.jpg
 [8]: http://dclure.org/wp-content/uploads/2014/03/200-miles-mapbox.jpg
 [9]: http://dclure.org/wp-content/uploads/2014/03/manhattan-person.jpg
 [10]: https://www.google.com/maps
 [11]: https://www.mapbox.com/
 [12]: http://www.bing.com/maps/
 [13]: http://google-latlong.blogspot.com/2013/06/only-clear-skies-on-google-maps-and.html
 [14]: http://www.bartelby.com/142/74.html