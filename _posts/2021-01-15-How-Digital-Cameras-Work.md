---
layout: post
title: How digital cameras work?
subtitle: The process behind image formation
cover-img: /assets/img/path.jpg
thumbnail-img: /assets/img/sensor.png
share-img: /assets/img/path.jpg
tags: [Camera, Sensor, Imaging, Photography]
---

Digital cameras were first developed in the 1970's with Kodak playing a very important role in their development. The fact that they failed to act on this turnt out to be
a not-so-good business decision in the long run. Digital cameras and sensors are ubiquitous today and can be found everywhere. So, in this article today we would be looking
to understand how light falling on an electronic camera sensor is converted to images that we see and share.

### Bayer filter

One of the most important discovies which lead to the development of colour imaging today would be the Bayer filter. It was developed by Bryce Bayer (also from Kodak) and 
without his invention we would still be left with only black and white images from our digital sensors. So, lets look into it's design in greater detail. A Bayer filter array
is a mosaic of red, green and blue filters that is placed over the image sensor. An image sensor is an array of various light-sensitive photosites - we wouldn't be delving 
into the design of the actual sensor itself. That would be another article for later.

<a title="The original uploader was Interiot at English Wikipedia., CC BY-SA 3.0 &lt;http://creativecommons.org/licenses/by-sa/3.0/&gt;, via Wikimedia Commons" href="https://commons.wikimedia.org/wiki/File:BayerPatternFiltration.png"><img width="256" alt="BayerPatternFiltration" src="https://upload.wikimedia.org/wikipedia/commons/f/ff/BayerPatternFiltration.png"></a>

So, in the image above, we can see a bayer filter in action. Each individual photosite is covered up by an individual colour filter - which can either be a red, green or blue
filter. These filters only allow either red or green or blue light to reach the actual photosite. This allows the camera sensor to record individual data pertaining to 
different colours on a photosite - which is then compiled via additional computation to get the full picture. From the picture above, we can see that the Bayer matrix consists
of a repeating pattern of 4 blocks - with one blue block, one red block and two green blocks. So, we can see that we have more green light gathering capacity - this is due
to the fact that our eyes are more sensitive to greenish light than it is to reds or blues. Thus in a way, the Bayer filter array mimics our eyes in the way we perceive colour.
Now, I would like to add at this point that the Bayer filter design is not the only available design. Fujifilm uses what they call a X-Trans sensor design. This is what it looks like

<a title="LiamUK at English Wikipedia, CC BY-SA 3.0 &lt;https://creativecommons.org/licenses/by-sa/3.0&gt;, via Wikimedia Commons" href="https://commons.wikimedia.org/wiki/File:Xtranscolourfilter.svg"><img width="256" alt="Xtranscolourfilter" src="https://upload.wikimedia.org/wikipedia/commons/thumb/f/ff/Xtranscolourfilter.svg/256px-Xtranscolourfilter.svg.png"></a>

As we can see, it is slightly different. But the underlying principle remains the same - get information regarding Red, Green and Blue light on individual photosites 
and then compile it to form the final image.

Small note : While Bayer filter is very popular today, we also have different sensor designs. One example of that would be the Foveon sensors - designed by Sigma.
A Foveon sensor allows us to capture information about red, green and blue colour - all on a single photosite. 

### Demosiacing
Upto this point, we were seeing how a camera sensor is able to see and distinguish colours. Now, it needs to use this data and give us an usable image. A Bayer sensor
gives us an output comprising of a mosaic of red, green and blue pixels - which is nowhere even close to how the human eyes see things. The process of converting this
mosaic of colours into an usable image is what we call "Demosaicing". 

<a title="MikeRun, CC BY-SA 4.0 &lt;https://creativecommons.org/licenses/by-sa/4.0&gt;, via Wikimedia Commons" href="https://commons.wikimedia.org/wiki/File:Bayer-frame-interpolation.png"><img width="512" alt="Bayer-frame-interpolation" src="https://upload.wikimedia.org/wikipedia/commons/9/91/Bayer-frame-interpolation.png"></a>

So, in order to calculate the true colour of each pixel - we need the data about intensity of red, green and blue light for each pixel. But, we only have information 
about a single colour for a single pixel. So, we need to fill in a few blanks and in order to do that we have to calculate colour information for all three colours at each pixel.
This is done via a process called interpolation. There are many different interpolation algorithms - some simple some more complex than the others. An example of simple
interpolation would involve copying the colour information from an adjacent cell. This is a very basic way and would result in a poor final image. A slightly more complex
way would be *bilinear interpolation*. In this method we can calculate the intensity of red colour at a non-red pixel by taking the average of two or four adjacent red
pixels. This is then done for green and blue as well and thus we finally have information about all the three colours for all pixels. We also have better, more complex
algorithms like *bicubic interpolatin, spline interpolation* and others. 

However, the problem with demosaicing is that we are guessing data that we did not have to begin it. As such, demosaicing results in problems like false colour aliasing
which were introduced by interpolation. We also come across the problem of speed vs quality - as a better algorithm would be more complex computationally which would reduce
output speeds. Balancing these aspects is a tough task indeed.

So, in conclusion, we have seen how a sensor is able to see colours and how we are able to convert this sensor data into an usable image. In the article, I briefly mentioned
Foveon sensors - we would look into it at a later date.
