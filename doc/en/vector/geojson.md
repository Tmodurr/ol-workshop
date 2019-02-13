# Rendering GeoJSON

Before getting into editing, we'll take a look at basic feature rendering with a vector source and layer.  The workshop includes a `countries.json` GeoJSON file in the `data` directory.  We'll start by just loading that data up and rendering it on a map.

First, edit your `index.html` so we're ready to render a full page map:

[import](../../../src/en/examples/vector/geojson.html)

Now we'll import the three important ingredients for working with vector data:

 * a format for reading and writing serialized data (GeoJSON in this case)
 * a vector source for fetching the data and managing a spatial index of features
 * a vector layer for rendering the features on the map

Update your `main.js` to load and render a local file containing GeoJSON features:

[import](../../../src/en/examples/vector/geojson.js)

You should now be able to see a map with country borders at {{book.workshopUrl}}/.

![GeoJSON features](geojson.png)

Since we'll be reloading the page a lot, it would be nice if the map stayed where we left it in a reload.  We can bring in the [`ol-hashed` package](https://www.npmjs.com/package/ol-hashed) to make this work.  Normally we'd install it first (though it should be included with the workshop dependencies already):

    npm install ol-hashed@beta

Then in our `main.js` we'll import the function exported by the package:

[import:'import'](../../../src/en/examples/vector/sync.js)

And now we can call this function with our map:

[import:'sync'](../../../src/en/examples/vector/sync.js)

Now you should see that page reloads keep the map view stable.  And the back button works as you might expect.
