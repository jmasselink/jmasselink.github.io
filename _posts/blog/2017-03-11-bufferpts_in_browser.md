---
layout: blog-post
category: Blog
title: "Buffering Points in the Browser"
author: "Joel Masselink"
twitter: j_masselink
permalink: /blog/
#2017/03/bufferpts_in_browser/
---

Recently I made a few base maps of various-sized buffers around ad hoc points. This type of request is quite common from my colleagues - draw a circle around a given point to understand relationships of *distance*.
> How many microbreweries are within a 5 mile radius from my home?
> How many cell towers with 10-km coverage are needed to provide service to a rural county?

I thought to myself - there must be a tool which allows one to drop a point on a map and see arbitrary distances, and to simply visualize these.

What I came up with is a basic workflow: using two tools together which harness the versatility of JavaScript object notation (GeoJSON) and the relative simplicity of tools which parse it:

[GitHub](https://www.github.com) Gists supports rendering GeoJSON in the browser.

Requirements:
1. Spatial data
2. Buffer calculation and visualization
3. Map styles

Steps:
1. [geojson.io](geojson.io) - allows for in-browser data editing and
2. [dropchop.io](dropchop.io) - built on the capability of turf.js and engineered by the folks at CUGOS, Dropchop is an in-browser GIS.
3. Mapbox styles
