---
title: The “Nicolay copy” of the Gettysburg Address
author: dm4fn
excerpt: '[Cross-posted from dclure.org] Launch the Exhibit This is a project that I&rsquo;ve been hacking away at for some time, but only found the time (and motivation) to get it polished up and out the door over the weekend &ndash; a digital edition of the &ldquo;Nicolay copy&rdquo; of the Gettysburg Address, with each of the ~250&hellip;. <a href="http://www.scholarslab.org/experimental-humanities/neatline-gettysburg-address/">More.</a>'
layout: post
permalink: /2014/02/04/the-nicolay-copy-of-the-gettysburg-address/
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
  - 'http://www.scholarslab.org/experimental-humanities/neatline-gettysburg-address/#comments'
"wfw:commentRSS":
  - http://www.scholarslab.org/experimental-humanities/neatline-gettysburg-address/feed/
syndication_feed:
  - http://www.scholarslab.org/tag/neatline/feed
syndication_feed_id:
  - 8
syndication_permalink:
  - http://www.scholarslab.org/experimental-humanities/neatline-gettysburg-address/
syndication_item_hash:
  - 74d64db04729ae04d6fd8c590efefd41
categories:
  - d3
  - Experimental Humanities
  - lincoln
  - neatline
---
<span class="Z3988" title="ctx_ver=Z39.88-2004&rft_val_fmt=info%3Aofi%2Ffmt%3Akev%3Amtx%3Adc&rfr_id=info%3Asid%2Focoins.info%3Agenerator&rft.type=&rft.format=text&rft.title=The+%22Nicolay+copy%22+of+the+Gettysburg+Address&rft.source=Scholars%26%23039%3B+Lab&rft.date=2014-02-04&rft.identifier=http%3A%2F%2Fwww.scholarslab.org%2Fexperimental-humanities%2Fneatline-gettysburg-address%2F&rft.language=English&rft.subject=Experimental+Humanities&rft.aulast=McClure&rft.aufirst=David"></span> 
*[Cross-posted from [dclure.org][1]]*

## [Launch the Exhibit][2]

[<img src="http://dclure.org/wp-content/uploads/2014/02/nicolay-fullscreen1.jpg" alt="nicolay-fullscreen" width="2880" height="1727" class="alignnone size-full wp-image-3661" />][2]



This is a project that I&#8217;ve been hacking away at for some time, but only found the time (and motivation) to get it polished up and out the door over the weekend &#8211; a digital edition of the [&#8220;Nicolay copy&#8221; of the Gettysburg Address][3], with each of the ~250 words in the manuscript individually traced out in Neatline and wired up with a plain-text transcription of the text on the right side of the screen. I&#8217;ve tinkered around with [similar interfaces][4] in the past, but this time I wanted to play around with different approaches to formalizing the connection between the digitally-typeset words in the text and the handwritten words in the manuscript. Your eyes tend to dart back and forth between the image and the text, and it&#8217;s easy to lose your place &#8211; how to reduce that cognitive friction?

To chip away at this, I wrote a little sub-plugin for Neatline called [WordLines][5], which automatically overlays a little visual guideline (under the hood, a [d3][6]-wrapped SVG `</p>
<line>` element) on top of the page that connects each pair of words in the two viewports when the cursor hovers on either of the instantiations. So, when the mouse passes over words in the transcription, lines are automatically drawn to the corresponding locations on the image; and vice versa. From a technical standpoint, this turns out to be quite easy &#8211; just get the pixel offsets for the `<span>` element in the transcription and the vector annotation on the map (for the latter, OpenLayers does the heavy lifting with helpers like `getViewPortPxFromLonLat`, which maps spatial coordinates to document-space pixel pairs), and then draw a line connecting the two points. The one hitch, though, is that this involves placing a large SVG element directly on top of the page content, which, by default, will cover all of the underlying elements (shapes on the map, words in the text) and block them from receiving the cursor events that drive the rest of the UI &#8211; including, very problematically, the `mouseleave` event that garbage-collects old lines and prevents them from getting stuck on the screen.

[<img src="http://dclure.org/wp-content/uploads/2014/02/wordline.jpg" alt="wordline" width="1470" height="678" class="alignnone size-full wp-image-3666" />][7]

The work-around is to put `pointer-events: none;` on the SVG element, which causes the browser to treat it as a purely visual veneer over the page &#8211; cursor events drop through to the underlying content elements, and everything else behaves normally. This is [just barely and only very recently cross-browser][8], but I&#8217;m not sure if there&#8217;s actually any other way to accomplish this, given the full set of constraints.

**Modeling intuitions about scale**

Originally, I had planned to just leave it at that, but, as is almost always the case with these projects, I ended up learning lots of interesting things along the way, and I ended up going back and adding in another set of annotations that make note of some of the more historically noteworthy aspects of the manuscript. Namely, I was interested in the different types of paper used for the two different pages (Lincoln probably wrote the first page in Washington before departing, the second page after arriving in Gettysburg) and the matching fold creases on the pages, which some historians have pointed to as evidence that the Nicolay copy was perhaps the actual &#8220;reading copy&#8221; that Lincoln used when delivering the speech, since eyewitness accounts describe Lincoln pulling a folded piece of paper out of his coat pocket.

The other candidate is the [Hay draft][9], which includes lots of changes and corrections in Lincoln&#8217;s hand, giving it the appearance of working draft that was prepared just before the event. One problem with the Hays draft, though, is its size &#8211; it&#8217;s written on larger paper and has just a single fold down the center, which would seem to make it an unlikely thing to tuck into coat pocket. When I read about this, I realized that I had paid almost no attention to the physical size of the manuscript. On the screen, it&#8217;s either extremely small or almost infinitely large &#8211; a tiny speck when you zoom far back, and an endless plane of beige-and-black when you zoom in. But, in this case, size turns out to be of great historical significance &#8211; the Nicolay copy is smaller than the Hays copy, especially when folded along the set of matching creases clearly visible on the pages.

So, how big is it? This involved a bit of guesswork. The resource page for the manuscript on the Library of Congress website doesn&#8217;t include dimensions, and direct Google searches didn&#8217;t turn up an easy answer, so I started poking around the internet to see if I could find other Lincoln manuscripts written on the &#8220;Executive Stationery&#8221; used for the first page. I rooted up a couple of documents for sale by rare book sellers, and in [both][10] [cases][11] the dimensions are listed at about 5 inches in width and 7-8 inches in height, meaning that the Nicolay copy &#8211; assuming the stationery was more or less standardized &#8211; would have folded down to a roughly 5 x 2.5-inch rectangle, which seems reasonably pocket-sized. (Again, this is amateur historical conjecture &#8211; if I&#8217;m wrong, please let me know!)

I sketched out little ruler annotations labeling the width of the page and the height of the fold segment, but, zooming around the exhibit, I realized that I still didn&#8217;t any intuitive sense of the size of the thing. Raw numerical measurements, even when you&#8217;re beat across the head with them, become surprisingly abstract in the a-physical, point-of-reference-less netherlands of deeply-zooming digital landscapes. I dug out a ruler and zoomed the exhibit back until the first page occupied five real-world inches, and then held my hand up to the screen, imagining the sheet of paper in my hand. And then I thought &#8211; why not just bake some kind of visual reference directly into the exhibit? I hunted down a CC-licensed SVG illustration of a handprint, and, using the size of my own hand as a reference, used Neatline&#8217;s import-SVG feature to position the outline in the whitespace to the right of the first page of the manuscript:

[<img src="http://dclure.org/wp-content/uploads/2014/02/hand2.jpg" alt="hand2" width="2106" height="1524" class="alignnone size-full wp-image-3664" />][12]

 [1]: http://dclure.org/logs/nicolay-copy-gettysburg-address/
 [2]: http://neatline.dclure.org/neatline/show/gettysburg-address
 [3]: http://prod.myloc.gov/Exhibitions/gettysburgaddress/exhibitionitems/ExhibitObjects/NicolayCopy.aspx
 [4]: http://neatline.dclure.org/neatline/show/saturn-v-stage-2
 [5]: https://github.com/davidmcclure/nl-widget-WordLines
 [6]: http://d3js.org/
 [7]: http://dclure.org/wp-content/uploads/2014/02/wordline.jpg
 [8]: http://caniuse.com/pointer-events
 [9]: http://prod.myloc.gov/Exhibitions/gettysburgaddress/exhibitionitems/ExhibitObjects/HayDraft.aspx
 [10]: http://www.baumanrarebooks.com/rare-books/lincoln-abraham/autograph-letter-signed/63126.aspx
 [11]: http://www.robertedwardauctions.com/auction/2006/1204.html
 [12]: http://dclure.org/wp-content/uploads/2014/02/hand2.jpg