---
layout:     post
title:      Roundabouts from MAPBOX
categories: GIS
---

## Roundbabouts from Mapbox (v2)

![Roundabouts - Spain]({{ site.url }}/media/2016/2016_02_24_RotondasEsp.jpg)

They can be seen on the following web page: https://www.mapbox.com/bites/00205/#5.53/39.705/-4.149



### On QGIS

To make them visible on QGIS use the following instructions:

- Install plugin TileLayer
- Follow instructions in https://cartoblography.wordpress.com/2015/04/28/using-custom-mapbox-baselayers-in-qgis/

Link to the plugin source code: https://github.com/minorua/TileLayerPlugin

### Setup fro QGIS

The general structure of the TSV file (to setup the layers seen from the tilelayer plugin) looks like:

{% highlight %}
MapboxStreets	Mapbox	http://api.tiles.mapbox.com/v4/mapbox.streets/{z}/{x}/{y}.png?access_token=pk.eyJ1IjoibWFwYm94IiwiYSI6ImNpamVuY3cxbzAwMG12ZGx4cGljbGtqMGUifQ.vpDqms08MBqoRgp667Yz5Q
MapboxRoundaboutsV	Mapbox	http://api.tiles.mapbox.com/v4/geohacker.roundabouts2/{z}/{x}/{y}.vector.pbf?access_token=pk.eyJ1IjoiZ2VvaGFja2VyIiwiYSI6ImFIN0hENW8ifQ.GGpH9gLyEg0PZf3NPQ7Vrg
MapboxRoundaboutsR	Mapbox	http://api.tiles.mapbox.com/v4/geohacker.roundabouts2/{z}/{x}/{y}.png?access_token=pk.eyJ1IjoiZ2VvaGFja2VyIiwiYSI6ImFIN0hENW8ifQ.GGpH9gLyEg0PZf3NPQ7Vrg
{% endhighlight %}
This one (vector style) doesn't work (with the tilelayer plugin) and it should be the way to go:
```
MapboxRoundaboutsV	Mapbox	http://api.tiles.mapbox.com/v4/geohacker.roundabouts2/{z}/{x}/{y}.vector.pbf?access_token=pk.eyJ1IjoiZ2VvaGFja2VyIiwiYSI6ImFIN0hENW8ifQ.GGpH9gLyEg0PZf3NPQ7Vrg
```
This one (raster) works
```
MapboxRoundaboutsR	Mapbox	http://api.tiles.mapbox.com/v4/geohacker.roundabouts2/{z}/{x}/{y}.png?access_token=pk.eyJ1IjoiZ2VvaGFja2VyIiwiYSI6ImFIN0hENW8ifQ.GGpH9gLyEg0PZf3NPQ7Vrg
```
### Transparency

The transparency can be modified on the QGIS layer properties



