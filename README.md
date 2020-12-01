# Taiwan Atlas TopoJSON

Similar to the [topojson/us-atlas](https://github.com/topojson/us-atlas) project, this repository provides a topojson redistribution of the shapefiles provided by Taiwan's Ministry of the Interior.

All of these files are provided at a scale of 1:10 thousand.

## File Reference

<a href="#villages-10t.json" name="villages-10t.json">#</a> <b>villages-10t.json</b> · [Download](https://cdn.jsdelivr.net/npm/taiwan-atlas/villages-10t.json "Source")

A [TopoJSON file](https://github.com/topojson/topojson-specification/blob/master/README.md#21-topology-objects) containing the geometry collections <i>villages</i>, <i>towns</i>, <i>counties</i>, and <i>nation</i>. The geometry is quantized and simplified, but not projected. This topology is derived from the Ministry of the Interior’s [村里界圖(TWD97經緯度)](https://data.gov.tw/dataset/7438). The town boundaries are computed by [merging](https://github.com/topojson/topojson-client/blob/master/README.md#merge) counties, the county boundaries by merging towns, and the nation boundary is computed by merging states, ensuring a consistent topology.

<a href="#towns-10t.json" name="towns-10t.json">#</a> <b>towns-10t.json</b> · [Download](https://cdn.jsdelivr.net/npm/taiwan-atlas/towns-10t.json "Source")

A [TopoJSON file](https://github.com/topojson/topojson-specification/blob/master/README.md#21-topology-objects) containing the geometry collections <i>towns</i>, <i>counties</i>, and <i>nation</i>. The geometry is quantized and simplified, but not projected. This topology is derived from the Ministry of the Interior’s [村里界圖(TWD97經緯度)](https://data.gov.tw/dataset/7438). The county boundaries are computed by [merging](https://github.com/topojson/topojson-client/blob/master/README.md#merge) towns, and the nation boundary is computed by merging states, ensuring a consistent topology.

<a href="#counties-10t.json" name="counties-10t.json">#</a> <b>counties-10t.json</b> · [Download](https://cdn.jsdelivr.net/npm/taiwan-atlas/counties-10t.json "Source")

A [TopoJSON file](https://github.com/topojson/topojson-specification/blob/master/README.md#21-topology-objects) containing the geometry collections <i>counties</i>, and <i>nation</i>. The geometry is quantized and simplified, but not projected. This topology is derived from the Ministry of the Interior’s [村里界圖(TWD97經緯度)](https://data.gov.tw/dataset/7438). The nation boundaries are computed by [merging](https://github.com/topojson/topojson-client/blob/master/README.md#merge) counties, ensuring a consistent topology.

<a href="#nation-10t.json" name="nation-10t.json">#</a> <b>nation-10t.json</b> · [Download](https://cdn.jsdelivr.net/npm/taiwan-atlas/nation-10t.json "Source")

A [TopoJSON file](https://github.com/topojson/topojson-specification/blob/master/README.md#21-topology-objects) containing the geometry collections <i>nation</i>. The geometry is quantized and simplified, but not projected. This topology is derived from the Ministry of the Interior’s [村里界圖(TWD97經緯度)](https://data.gov.tw/dataset/7438).

<a href="#tw.objects.nation" name="tw.objects.nation">#</a> tw.objects<b>nation</b>
<img src="https://raw.githubusercontent.com/dkaoster/taiwan-atlas/master/img/nation.svg" width="130.09" height="178.35">

The nation object has no fields.

<a href="#tw.objects.counties" name="tw.objects.counties">#</a> tw.objects<b>counties</b>
<img src="https://raw.githubusercontent.com/dkaoster/taiwan-atlas/master/img/county.svg" width="130.09" height="178.35">

The county object has three fields:
- county.properties.COUNTYNAME - The name of the county
- county.properties.COUNTYID - The character specifying id
- county.properties.COUNTYCODE - The five digit county code

<a href="#tw.objects.towns" name="tw.objects.towns">#</a> tw.objects<b>towns</b>
<img src="https://raw.githubusercontent.com/dkaoster/taiwan-atlas/master/img/towns.svg" width="130.09" height="178.35">

The town object has three fields in addition to the county fields:
- town.properties.TOWNNAME - The name of the county
- town.properties.TOWNID - The character specifying id
- town.properties.TOWNCODE - The eight digit county code

<a href="#tw.objects.villages" name="tw.objects.villages">#</a> tw.objects<b>villages</b>
<img src="https://raw.githubusercontent.com/dkaoster/taiwan-atlas/master/img/villages.svg" width="130.09" height="178.35">

The village object has three fields in addition to the town and county fields:
- village.properties.VILLNAME - The name of the village
- village.properties.VILLID - The village specifying id
- village.properties.VILLCODE - The 11 digit county code

## MercatorTw Projection

`mercatorTw.js` uses a Taiwan-centric composite projection of four [d3.geoMercator](https://github.com/d3/d3-geo#geoMercator) projections: One for the main island, and one for each of Penghu, Kinmen, Lienchiang, and Wuqiu respectively.

This package exports the mercatorTw projection and can be used in your own projects.

```js
import mercatorTw from 'taiwan-atlas';
```

## License
MIT