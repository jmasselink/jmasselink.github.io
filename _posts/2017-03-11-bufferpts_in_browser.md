---
layout: blog-post
category: blog
title: "Buffering Points in the Browser"
author: "Joel Masselink"
twitter: j_masselink
image: /images/blogheaders/2017-03-sotmus_dates.jpg
permalink: /2017/03/bufferpts_in_browser/
---

------------
I work at Vulcan, which is a very diverse company,
------------

Recently I made a few base maps of various-sized buffers around ad hoc points. The question is common - draw a circle around a given point to understand  relationships of *distance*. How many microbreweries are within a 5 mile radius from my home? How many cell towers with 10-km coverage are needed to provide service to a rural county?

Open-source desktop GIS has never been more powerful, accessible, and capable. In particular, [QGIS](http://www.qgis.org) provides wonderful capabilities for data manipulation, editing, management, and cartography. I use QGIS every day and developers continue to enhance, modernize, and to make this the one desktop GIS software that I cannot do without.

I thought to myself - there must be a tool which allows one to drop a point on a map and see arbitrary distances, and to simply visualize these.

What I came up with is a basic workflow: linking tools together which harness the versatility of JavaScript object notation (GeoJSON) and simplicity of tools which parse it.
 [GitHub](https://www.github.com)
But it can take time


1. Spatial data
2. Buffer calculation and visualization
3. Map styles

1. geojson.io - allows for in-browser data editing and
2. dropchop.io - built on the capability of turf.js and engineered by the folks at CUGOS, Dropchop is an in-browser GIS.
3. Mapbox styles

Steps -




You can always contact us directly at [sotmus@openstreetmap.us](mailto:sotmus@openstreetmap.us) for general inquiries, to join the working group, information about the sponsorship pipeline, or anything else. To sign up for updates, follow us on [Twitter](https://twitter.com/sotmus), talk with us [on Slack](https://osmus-slack.herokuapp.com/), and [subscribe to our newsletter](http://eepurl.com/bTWSqr).

See you this fall in Boulder!
