---
title: “The Song of Wandering Aengus,” Neatline, and negotiation with the machine
author: dm4fn
excerpt: '[Cross-posted from dclure.org] Click here to view the exhibit. One last little experiment with Neatline-powered interactive typesettings &ndash; this time with the ending of Yeats&rsquo; endlessly recitable &ldquo;The Song of Wandering Aengus,&rdquo; which, like many great poems, seems to somehow signify the entire world and nothing really in particular. I chose to use just the&hellip;. <a href="http://www.scholarslab.org/experimental-humanities/song-of-wandering-aengus/">More.</a>'
layout: post
permalink: /2013/10/11/the-song-of-wandering-aengus-neatline-and-negotiation-with-the-machine/
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
  - 'http://www.scholarslab.org/experimental-humanities/song-of-wandering-aengus/#comments'
"wfw:commentRSS":
  - http://www.scholarslab.org/experimental-humanities/song-of-wandering-aengus/feed/
syndication_feed:
  - http://www.scholarslab.org/tag/neatline/feed
syndication_feed_id:
  - 8
syndication_permalink:
  - http://www.scholarslab.org/experimental-humanities/song-of-wandering-aengus/
syndication_item_hash:
  - 6530b42c367058ffa070171ac188ce17
  - b78ed803df1b2a6da45d33b32d1eeff3
categories:
  - Experimental Humanities
  - neatline
  - yeats
---
<span class="Z3988" title="ctx_ver=Z39.88-2004&rft_val_fmt=info%3Aofi%2Ffmt%3Akev%3Amtx%3Adc&rfr_id=info%3Asid%2Focoins.info%3Agenerator&rft.type=&rft.format=text&rft.title=%22The+Song+of+Wandering+Aengus%2C%22+Neatline%2C+and+negotiation+with+the+machine&rft.source=Scholars%26%23039%3B+Lab&rft.date=2013-10-11&rft.identifier=http%3A%2F%2Fwww.scholarslab.org%2Fexperimental-humanities%2Fsong-of-wandering-aengus%2F&rft.language=English&rft.subject=Experimental+Humanities&rft.aulast=McClure&rft.aufirst=David"></span> 
*[Cross-posted from [dclure.org][1]]*

## [Click here to view the exhibit][1].



One last little experiment with Neatline-powered interactive typesettings &#8211; this time with the ending of Yeats&#8217; endlessly recitable &#8220;The Song of Wandering Aengus,&#8221; which, like many great poems, seems to somehow signify the entire world and nothing really in particular. I chose to use just the last three lines so that it would be possible to play with a more dramatic type of geometric nesting that, with more content, would quickly run up against the technical limitation that I mentioned in [Wednesday&#8217;s post about &#8220;A Coat&#8221;][2] &#8211; the vector geometry used to form the letters starts to degrade as the Javascript environment runs out of decimal precision at around 40 levels of zoom, making it impossible to continue the downward beyond a certain point.

With just three lines, though, I was able to place each consecutive line completely inside of one of the dots above an &#8220;i&#8221; in the previous line. So, the &#8220;silver apples of the moon&#8221; are inscribed into the dot over the &#8220;i&#8221; in the &#8220;till&#8221; of &#8220;till time and times are done,&#8221; and the &#8220;golden apples of the moon&#8221; are then contained by the dot on the &#8220;i&#8221; in &#8220;silver.&#8221; Since the nested lines are placed literally inside the shaded boundaries of letters (as opposed to the empty spaces delineated by the &#8220;holes&#8221; in letters, as was the case with the [first][2] [two][3] experiments), the color of the text has to alternate in order to be legible against the changing color of the backdrop. What I didn&#8217;t expect (although in retrospect I guess it&#8217;s obvious) is that this shift in the color palette completely modulates the visual temperature of the whole environment &#8211; the backdrop swerves from bright white to solid black back and then back to white over the course of the three lines, with the last transition mapping onto the night-to-day, moon-to-sun thematic movement in the final couplet.

Interestingly, this effect was almost thwarted by another unexpected quirk in the underlying technologies, although I managed to maneuver around it with a little hack in the exhibit theme. The problem was this &#8211; it turns out that OpenLayers will actually stop rendering an SVG geometry ones the dimension of the viewport shrinks down below a certain ratio relative to the overall size of the shape. So, in this case, as the camera descends down into the black landscape of the dot over the first &#8220;i,&#8221; the black background supplied by the vector shape would suddenly drop away, as if the camera were falling through the surface, which of course had the effect of making the second-to-last line &#8211; typeset in white &#8211; suddenly invisible against the default-white background of the exhibit.

I thought this was a showstopper, but then I realized that I could programmatically &#8220;fake&#8221; the black background by directly flipping the CSS `background` color on the exhibit container. So, I just fired up the Javascript console, inspected the `zoom` attribute on the OpenLayers instance to get the zoom thresholds where the color changes needed to happen, and then dropped a little chunk of custom code into the [exhibit theme][4] that manifests the style change in response to the zoom events triggered by the map:



Weird, but effective. Whenever I work on projects like these I&#8217;m fascinated by the wrinkles that arise in the interaction between what you want to do and what the technology allows you to do. It&#8217;s very different from analog scholarship or art practice, where you have a more complete mastery over the field of play &#8211; you have a much more direct and unmediated control over the sound of your words, the shape of a line in a physical sketch, the pressure of a brush stroke. With digital objects, though, you&#8217;re building on top of almost unimaginably huge stacks of technology &#8211; the millions of man-hours of work that it took to create the vast ecosystem of Javascript and PHP libraries that Neatline depends on, the whole set of lower-level technologies that shape the underlying browser rendering engines and Javascript runtimes, which in turn are implemented in still lower-level languages, which eventually brush up against the dizzying rabbit hole of physical hardware engineering, which to my mind is about as close to magic as anything that people have produced.

That kind of deep, massively-distributed collaboration can definitely exist offscreen (eg., all of intellectual history, in a sense), but it&#8217;s more loosely coupled, and certainly less fragile &#8211; if I write an essay about Yeats, Yeats can&#8217;t *break* in the way that a code dependency literally can (will). At first this really bothered me, but I&#8217;ve come to peace with it &#8211; digital work is by definition a relinquishing of control, a give-and-take with the machine, a negotiation with our current little slice of modernity about what&#8217;s possible.

 [1]: http://neatline.dclure.org/neatline/show/song-of-wandering-aengus
 [2]: http://dclure.org/essays/more-fun-with-interactive-typesetting-a-coat-by-yeats/
 [3]: http://dclure.org/essays/experimental-typesetting-with-neatline-and-shakespeare/
 [4]: https://github.com/davidmcclure/neatlight/tree/master/neatline/exhibits/themes/song-of-wandering-aengus