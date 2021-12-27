
Google Earth Engine is a **cloud-based platform** for earth science and analysis. It helps with managing a lot of geospatial datasets.

What can GEE can do?
- Get an image
- apply an algorithm to an image
- filter a collection (series of images)
- map an algorithm over a collection
- reduce a collection
- compute aggregate statistics

Among the different geospatial processing functions you can perform are the following:
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

![Image](https://i.ibb.co/p1Xp4MD/Captura-2.jpg)

-->and press "import"

![Image](https://i.ibb.co/H7my9jW/Captura-3.jpg)

--> this dataset becomes available as a VARIABLE

![Image](https://i.ibb.co/g48NprM/Captura-4.jpg)

### 2. Adding Layers:

Once we have imported the product we are interested in (e.g. SRTM), we add it by typing:

```Map.addLayer(srtm);
```

On this layer (SRTM), we can add more info. If we enter Map.addLayer and then click (Ctrl + space) the following parameters will appear:
```Map.addLayer(eeObject, visParams, name, shown, opacity)
```

- eeObject --> this parameters relates to the product we add as a new layer (e.g. SRTM)
- visParams --> This parameter relates to the visualisation of the object. Basically it determines how this will look. 
- name -->

