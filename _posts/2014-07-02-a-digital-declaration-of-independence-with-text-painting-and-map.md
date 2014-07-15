---
title: A (Digital) Declaration of Independence
author: dm4fn
excerpt: '[Cross-posted from dclure.org] Launch the Exhibit Way back in the spring of 2012, a couple months before we released the first version of Neatline, I drove up to Washington to give a little demo of the project to the folks at the Library of Congress. I had put together a couple of example exhibits for&hellip;. <a href="http://www.scholarslab.org/geospatial-and-temporal/a-digital-declaration-of-independence-with-text-painting-and-map/">More.</a>'
layout: post
permalink: /2014/07/02/a-digital-declaration-of-independence-with-text-painting-and-map/
syndication_source_uri:
  - http://www.scholarslab.org
enclosure:
  - |
    |
        
        
        
syndication_source:
  - 'Scholars&#039; Lab » neatline'
syndication_source_id:
  - http://www.scholarslab.org/tag/neatline/feed
"rss:comments":
  - 'http://www.scholarslab.org/geospatial-and-temporal/a-digital-declaration-of-independence-with-text-painting-and-map/#comments'
"wfw:commentRSS":
  - http://www.scholarslab.org/geospatial-and-temporal/a-digital-declaration-of-independence-with-text-painting-and-map/feed/
syndication_feed:
  - http://www.scholarslab.org/tag/neatline/feed
syndication_feed_id:
  - 8
syndication_permalink:
  - http://www.scholarslab.org/geospatial-and-temporal/a-digital-declaration-of-independence-with-text-painting-and-map/
syndication_item_hash:
  - 422a3f2a3be0b71c72ecd92f20c10e5f
  - 3ebbaccb22f9c35e5fa0da6e11cc5d7a
  - e8db8d1373b5d1342adc51db75dcde10
  - bc522a6555b419a2b1a8c4a26c66a70e
  - 4977e58d008852ef318db6041d117fcc
categories:
  - Geospatial and Temporal
  - neatline
  - react
---
<span class="Z3988" title="ctx_ver=Z39.88-2004&rft_val_fmt=info%3Aofi%2Ffmt%3Akev%3Amtx%3Adc&rfr_id=info%3Asid%2Focoins.info%3Agenerator&rft.type=&rft.format=text&rft.title=A+%28Digital%29+Declaration+of+Independence&rft.source=Scholars%26%23039%3B+Lab&rft.date=2014-07-02&rft.identifier=http%3A%2F%2Fwww.scholarslab.org%2Fgeospatial-and-temporal%2Fa-digital-declaration-of-independence-with-text-painting-and-map%2F&rft.language=English&rft.subject=Geospatial+and+Temporal&rft.aulast=McClure&rft.aufirst=David"></span> 
*[Cross-posted from [dclure.org][1]]*

## [Launch the Exhibit][2]

[<img src="http://dclure.org/wp-content/uploads/2014/07/declaration-of-independence-1024x610.jpg" alt="declaration-of-independence" width="640" height="381" class="alignnone size-large wp-image-3927" />][2]

Way back in the spring of 2012, a couple months before we released the first version of Neatline, I drove up to Washington to give a little demo of the project to the folks at the Library of Congress. I had put together a couple of example exhibits for the presentation, but, the night before, I was bored and found myself brainstorming about Washington-themed projects. On a lark, I downloaded a [scan of the 1823 facsimile of the Declaration of Independence][3] from the National Archives website, and spent a couple hours tracing polygons around each one of the signatures at the bottom of the document. I showed the exhibit the next day, and had big plans to flesh it out and turn it into a real, showable project. But then I got swept up in the race to get the first release of Neatline out the door before DH2012 in Hamburg, and then sucked into the craziness of the summer conference season, and the project slipped down into the towering stack of things that I could never quite find time to work on.

For some reason, though, the idea popped back into my head a couple months ago &#8211; maybe because Menlo Park is submerged in a kind of permanent summer, and it pretty much always feels like a good time to eat ice cream and shoot off fireworks. After mulling it over for a couple weeks, I decided to resurrect it from the dead, spruce it up, and post it in time for the 4th of July. So, with two days to spare, here we go &#8211; an interactive edition of the Declaration of Independence, tightly coupled with three other &#8220;views&#8221; in an effort to add dimension to the original document:

1.  A full-text, two-way-linked transcription of the manuscript and the signatures at the bottom. Click on sentences in the transcription to focus on the corresponding region of the scanned image, or click on annotated blocks on the image to scroll the text. 
    [<img src="http://dclure.org/wp-content/uploads/2014/07/transcript-1024x620.jpg" alt="transcript" width="640" height="387" class="alignnone size-large wp-image-3931" />][4] </li> 
    *   An interactive edition of [Trumbull&#8217;s &#8220;Declaration of Independence&#8221; painting][5], with each of the faces outlined and interactively linked with the corresponding signature on the document. 
        [<img src="http://dclure.org/wp-content/uploads/2014/07/painting1-1024x616.jpg" alt="painting" width="640" height="385" class="alignnone size-large wp-image-3940" />][6] </li> 
        *   All of which is plastered on top of a map that plots out each of the signers&#8217; hometowns on a custom [Mapbox][7] layer, which makes it easy to see how the layout of the signatures maps on to the geographic layout of the colonies. Which, by extension, tracks the future division between Union and Confederate states in the Civil War &#8211; Georgia and the Carolinas look awful lonely over on the far left side of the document. 
            [<img src="http://dclure.org/wp-content/uploads/2014/07/map1-1024x615.jpg" alt="map" width="640" height="384" class="alignnone size-large wp-image-3939" />][8] </li> </ol> 
            Once I positioned the layers, annotated the signatures and faces, and plotted out the hometowns, I realized that I had painted myself into an interesting little corner from an information design standpoint &#8211; it was difficult to quickly move back and forth between the three main sections of the exhibit. In a sense, this is an inherent characteristic of deeply-zoomed interfaces. The ability to focus really closely on any one of the three visual grids &#8211; which is what makes it possible to mix them all together into a single environment &#8211; has the side effect of making the other two increasingly distant and inaccessible, more and more so the further down you go. For example, once you&#8217;ve focused in on Thomas Jefferson&#8217;s face in the Trumbull painting, it&#8217;s quite a chore to manually navigate to the corresponding signature on the document &#8211; you have to zoom back, pan the map up towards the scanned image, find the signature (often no easy task), and then zoom back down.
            
            This is especially annoying in this case, since this potential for *comparison* is a big part of what&#8217;s interesting about the content. What I really wanted, I realized, was to be able to switch back and forth in a really simple, fluid way among the different instantiations of any individual person on the document, painting, and map &#8211; I wanted to be able to flip through them like a slideshow, to round up all the little partial representations of the person and hold them side-by-side in my head. So, as an experiment, I whipped up a little batch of custom UI components (built with the excellent [React][9] library, which fits in like a dream with Neatline&#8217;s Javascript API) that provide a &#8220;toggling&#8221; interface for each individual signer, and the exhibit as a whole.
            
            By default, when you hit the page, three top-level buttons in the right corner of the window link to the the three main sections of the exhibit &#8211; the hometowns plotted along the eastern seaboard, the declaration over the midwest, and the painting over the southeast. In addition to the three individual buttons, there&#8217;s also a little &#8220;rotate&#8221; button that automatically cycles through the three regions, which makes it easy to toggle around without looking away from the map to move the cursor:
            
            [<img src="http://dclure.org/wp-content/uploads/2014/07/exhibit-buttons.jpg" alt="exhibit-buttons" width="603" height="138" class="alignnone size-full wp-image-3937" />][10]
            
            More useful, though, it&#8217;s possible to bind any of the individual signers to the widget by clicking on the annotations. For example, if I click on Thomas Jefferson&#8217;s face in the painting, the name locks into place next to the buttons, which now point to the representations of that specific person in the exhibit &#8211; &#8220;Text&#8221; links to Jefferson&#8217;s signature, &#8220;Painting&#8221; to his face, and &#8220;Map&#8221; to Monticello:
            
            [<img src="http://dclure.org/wp-content/uploads/2014/07/signer-toggle-1024x840.jpg" alt="signer-toggle" width="640" height="525" class="alignnone size-large wp-image-3942" />][11]
            
            Once you&#8217;ve activated one of the signers, click on the name to show an overlay with a picture and biography, pulled from a public domain book published by the National Park Service called Signers of the Declaration:
            
            [<img src="http://dclure.org/wp-content/uploads/2014/07/bio-overlay-1024x624.jpg" alt="bio-overlay" width="640" height="390" class="alignnone size-large wp-image-3943" />][12]
            
            This is pretty straightforward on the map and document, where there&#8217;s always a one-to-one correspondence between an annotation and one of the signers. Things get more complicated on the map, though, where it&#8217;s possible for a single location to be associted with more than one signer. Philadelphia, for example, was home to Robert Morris, Benjamin Rush, Benjamin Franklin, John Morton, and George Clymer, so I had to write a little widget to make it possible to hone in on just one of the five after clicking the dot:
            
            [<img src="http://dclure.org/wp-content/uploads/2014/07/philadelphia-1024x377.jpg" alt="philadelphia" width="640" height="235" class="alignnone size-large wp-image-3945" />][13]
            
            Last but not least, each sentence in the document itself is annotated and wired up with the corresponding text transcription on the left &#8211; click on the image to scroll the text, or click on the text to focus the image:
            
            [<img src="http://dclure.org/wp-content/uploads/2014/07/text-1024x617.jpg" alt="text" width="640" height="385" class="alignnone size-large wp-image-3947" />][14]
            
            Happy fourth!

 [1]: http://dclure.org/essays/a-digital-declaration-of-independence-with-text-painting-and-map/
 [2]: http://neatline.dclure.org/neatline/show/declaration-of-independence
 [3]: http://www.archives.gov/exhibits/charters/declaration_transcript.html
 [4]: http://dclure.org/wp-content/uploads/2014/07/transcript.jpg
 [5]: http://en.wikipedia.org/wiki/Trumbull%27s_Declaration_of_Independence
 [6]: http://dclure.org/wp-content/uploads/2014/07/painting1.jpg
 [7]: https://www.mapbox.com/
 [8]: http://dclure.org/wp-content/uploads/2014/07/map1.jpg
 [9]: http://facebook.github.io/react/
 [10]: http://dclure.org/wp-content/uploads/2014/07/exhibit-buttons.jpg
 [11]: http://dclure.org/wp-content/uploads/2014/07/signer-toggle.jpg
 [12]: http://dclure.org/wp-content/uploads/2014/07/bio-overlay.jpg
 [13]: http://dclure.org/wp-content/uploads/2014/07/philadelphia.jpg
 [14]: http://dclure.org/wp-content/uploads/2014/07/text.jpg