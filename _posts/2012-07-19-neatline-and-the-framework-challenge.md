---
title: Neatline and the framework challenge
author: clured
layout: post
permalink: /2012/07/19/neatline-and-the-framework-challenge/
categories:
  - Neatline News
---
With the first public release of [Neatline][1] out the door, I&#8217;ve had the chance to take a short break from programming and think back over the nine-month development cycle that led up to the launch. In retrospect, I think that a lot of the exciting challenges we ran up against &#8211; the big, difficult questions about *what* to program, as opposed to *how* to program &#8211; emerged from tensions that are inherent in the task of creating frameworks as opposed to conventional applications.

What&#8217;s a framework? As an experiment, I&#8217;ll define the term broadly to mean applications that make it possible to *create things*, as opposed to applications that make it possible to *accomplish tasks*. Frameworks are generative in a way that normal applications are not. Instead of controlling systems, crunching numbers, automating processes, boosting efficiency, or providing entertainment, frameworks are set apart by the fact that the allow the user to spawn off new things that are independent of the software itself. 

Microsoft Word is used to create **documents**; WordPress is used to create **blogs** and **blog posts**; Drupal is used to create **websites**; Ruby on Rails is used to build **web applications**; Illustrator is used to create **vector graphics**; Maya is used to create **3d models and animations**.

Omeka and Neatline fit straightforwardly into this definition. Omeka is used to build online digital collections; Neatline, a framework-within-a-framework built on top of Omeka, is used to create interactive maps and timelines. In each case, the final unit of analysis is some sort of discrete, addressable thing that is generated with the assistance of the software. It can be viewed, visited, or printed. Frameworks empower users to create things that would be difficult or completely impossible to create without the assistance of the software.

The paradox, though, is that frameworks have to simultaneously constrict the user&#8217;s agency in the act of expanding it. Barring some kind of mythological ur-framework that would allow for direct, unmediated, and unbounded realization of thought (Prospero&#8217;s book of magic), all frameworks, whether implicitly or explicitly, have to define a range of final outputs that will be &#8220;supported&#8221; by the software. In practice, this means paring down the supported outputs to a vanishingly small subset of the original possibility space. Frameworks are defined as much by what they disallow as by what they allow.

For the developer, deciding on the &#8220;range&#8221; of the framework is a difficult and sometimes agonizing process because it involves a fundamental tradeoff between *power* and *accessibility* &#8211; and, by extension, the size of the potential audience. As a framework becomes more powerful and allows a wider range of possible outputs, it also becomes more complex and locks out users who aren&#8217;t willing to invest the effort to become proficient with the tool. As a framework becomes more narrow and focused, a larger number of people will be able and willing to use it, but the diversity of the final outputs drops, and the tool becomes suitable for a much smaller range of use cases. It&#8217;s a zero-sum game.

Over the course of the last couple months, I&#8217;ve realized that this opposition between power and ease-of-use provides an interesting vocabulary for defining Neatline and situating it in the ecosystem of existing geospatial tools. Up until now, it seems to me that existing frameworks have clustered around the two ends of the power / ease-of-use spectrum. Consumer web applications like the Google mapmaker allow the user to drop pins and annotate them with short captions. This is delightfully easy, but all of the end-products look the same, and the tool doesn&#8217;t really provide a critical mass of flexibility and the opportunity for real intellectual ownership that&#8217;s required for serious scholarly use.

Meanwhile, at the other end of the spectrum, desktop GIS applications like ArcMap provide an incredibly powerful and feature-rich platforms for analyzing geospatial data and creating visualizations. For projects that have access to custom software development, programming libraries like [OpenLayers][2], [Leaflet][3], [PolyMaps][4], and [Timeglider][5] provide flexible, highly-customizable toolkits for creating interactive maps and timeline &#8211; but only at the level of code.

There&#8217;s been an underpopulated zone in the middle the spectrum, though &#8211; not many spatio-temporal tools have tried to more evenly balance power and accessibility. Neatline tries to land in a &#8220;goldilocks&#8221; zone between the two poles. It tries to be simple enough out-of-the-box that it can be used by a large majority of scholars and students who do not have programming experience or advanced GIS expertise, but still complex enough to allow for significant diversity in the structure and style of the final output.

This means, of course, that Neatline *could* be more powerful and *could* be easier to use. My argument, though, is that it couldn&#8217;t both &#8211; at least, not without tripping over itself and breaking apart into incoherence.

Instead of choosing one pole at the expense of the other, we decided to make a studious attempt to balance the two. This is difficult to do &#8211; perhaps more difficult than committing wholesale to one or the other, which can often have the effect of locking in a cascading series of almost automatic design decisions leading towards a more singular objective. Building &#8220;middle-ground&#8221; frameworks requires a constant (re-)calibration of the feature set over the course of the development process, a sort of gyroscopic vigilance to keep the software perched in the tricky zone between flexibility and accessibility.

Like all real challenges, though, this one was also fantastically exciting to tackle. Now that Neatline is out in the wild, I can&#8217;t wait to see what people create with it.

 [1]: http://neatline.org/
 [2]: http://openlayers.org/
 [3]: http://leaflet.cloudmade.com/
 [4]: http://polymaps.org/
 [5]: http://timeglider.com/jquery/