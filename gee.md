---
title: "GEE"
tags: ""
---

Google Earth Engine is a **cloud-based platform** for earth science and analysis. It helps with managing a lot of geospatial datasets.

What can GEE do? 
Some of the functionalities that GEE is capable of are the followings:
- Get an image
- Apply an algorithm to an image
- Filter a collection (series of images)
- Map an algorithm over a collection
- Reduce a collection
- Compute aggregate statistics
Among the different geospatial processing functions you can perform with GEE are the following:
- Image collection
- Filter
- Reducer
- Join
- Export
- etc

*GEE Data Catalog*
- Landsat & Sentinel
- MODIS
- Terrain and Land Cover
- Weather & Climate

### 1. Image Collection:

-> Enter the dataset you are interested in
![Captura_2.JPG](https://boostnote.io/api/teams/b_PuTqecE/files/c1c571bbb9984dee54e220261de2e0e1fd0b22d8e2345be9c62b027204d890ed-Captura_2.JPG)

-->and press "import"
![Captura_3.JPG](https://boostnote.io/api/teams/b_PuTqecE/files/2bd5790fc758357b2c6194ce9728f3e6fbb27067d6eb9c79cfb944ee69e547c2-Captura_3.JPG)

--> this dataset becomes available as a VARIABLE

![Captura_4.JPG](https://boostnote.io/api/teams/b_PuTqecE/files/93e04a18881efbb969ca12eac1b313e9258ef475eed0a5fd49725266a74f22ff-Captura_4.JPG)


### 2. Adding Layers:

Once we have **imported** the product we are interested in (e.g. SRTM), we **display** it by typing:
`Map.addLayer(srtm);`

On this layer (SRTM), we can add more info. If we enter `Map.addLayer` and then click (Ctrl + space) the following parameters will appear:
`Map.addLayer(eeObject, visParams, name, shown, opacity)`

- eeObject --> this parameters refers to the product we add as a new layer (e.g. SRTM)
- visParams --> This parameter refers the visualisation of the object. Basically it determines how this will look. 
- name --> This parameter refers to the name of the layer we want to add.  
- shown --> Parameter used to turn your layer on or off. If it's off, your layer will appear as invisible. By default is on.
- opacity --> Parameter to control the level of opacity of the image you are overlaying

eeObject = srtm
visParams = {min:0, max:3000} => data elevation for srtm. This data is in meters. 
name = srtm. As soon as we enter the name of this new layer it will show up on the "layer" tab menu.

`Map.addLayer(srtm, {min:0, max:3000}, 'srtm');`

We can also customise the visualisation by adding **colour**.
`Map.addLayer(srtm, {min:0, max:3000, palette:'yellow, purple'}, 'srtm');`. If you want to add additional colours to the palette, the default pallette assigns the first colour to the lowest values, and the last colour to the upper values, and then interpolates in between.
`Map.addLayer(srtm, {min:0, max:3000, palette:'yellow,blue, grey, purple'}, 'srtm');`. For more info check out [here](https://developers.google.com/earth-engine/guides/image_visualization)

Now we are adding a new layer for water:
`Map.addLayer(water, {bands:'occurrence', min:0, max:100, palette:'lightblue, blue'}, 'water');`

To better appreciate the **srtm** and **water** values, we can search for the grand canyon (USA) and see what it looks like:
(https://boostnote.io/api/teams/b_PuTqecE/files/8d910b066ade7530f020cf9320aba62d930fbddab22a36b179ac7eff39ca1469-Captura_1.JPG)

![Image](https://i.ibb.co/sKwpcqw/Captura-5.jpg)

Something interesting to note at this point is that we can check any raster value by using the **inspector** tool provided by GEE on the right side menu.

![Image](https://i.ibb.co/tx1Sxk3/Captura-6.jpg)

Additionally to these layers we can also add 'slope' to better reflect elevation variation. For this purpose we will enter a new variable called 'slope':
`var slope = ee.Terrain.slope(srtm)`
And in order to visualise this new layer, once again, we will proceed as follows:
`Map.addLayer(slope, {min:0, max:45},'slope');`

**2. Units**
If you are not sure what min and max values you should select
