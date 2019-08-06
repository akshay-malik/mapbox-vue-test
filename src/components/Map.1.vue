<template>
  <div id="map" >
   </div>
</template>

<script>

import mapboxgl from 'mapbox-gl'
import axios from 'axios'

var cityStreets_0_401k = 'https://services.arcgis.com/fLeGjb7u4uXqeF9q/arcgis/rest/services/Street_Centerline/FeatureServer/0/query?where=SEG_ID+%3C+401000&objectIds=&time=&geometry=&geometryType=esriGeometryEnvelope&inSR=&spatialRel=esriSpatialRelIntersects&resultType=none&distance=0.0&units=esriSRUnit_Meter&returnGeodetic=false&outFields=SEG_ID&returnGeometry=true&featureEncoding=esriDefault&multipatchOption=none&maxAllowableOffset=&geometryPrecision=&outSR=4326&datumTransformation=&applyVCSProjection=false&returnIdsOnly=false&returnUniqueIdsOnly=false&returnCountOnly=false&returnExtentOnly=false&returnQueryGeometry=false&returnDistinctValues=false&cacheHint=false&orderByFields=&groupByFieldsForStatistics=&outStatistics=&having=&resultOffset=&resultRecordCount=&returnZ=false&returnM=false&returnExceededLimitFeatures=true&quantizationParameters=&sqlFormat=standard&f=pgeojson&token='
var cityStreets_401k_541k = 'https://services.arcgis.com/fLeGjb7u4uXqeF9q/arcgis/rest/services/Street_Centerline/FeatureServer/0/query?where=SEG_ID+%3E%3D++401000+AND+SEG_ID+%3C+541000&objectIds=&time=&geometry=&geometryType=esriGeometryEnvelope&inSR=&spatialRel=esriSpatialRelIntersects&resultType=none&distance=0.0&units=esriSRUnit_Meter&returnGeodetic=false&outFields=SEG_ID&returnGeometry=true&featureEncoding=esriDefault&multipatchOption=none&maxAllowableOffset=&geometryPrecision=&outSR=4326&datumTransformation=&applyVCSProjection=false&returnIdsOnly=false&returnUniqueIdsOnly=false&returnCountOnly=false&returnExtentOnly=false&returnQueryGeometry=false&returnDistinctValues=false&cacheHint=false&orderByFields=&groupByFieldsForStatistics=&outStatistics=&having=&resultOffset=&resultRecordCount=&returnZ=false&returnM=false&returnExceededLimitFeatures=true&quantizationParameters=&sqlFormat=standard&f=pgeojson&token='
var cityStreets_541k_721k = 'https://services.arcgis.com/fLeGjb7u4uXqeF9q/arcgis/rest/services/Street_Centerline/FeatureServer/0/query?where=SEG_ID+%3E%3D++541000+AND+SEG_ID+%3C+721000&objectIds=&time=&geometry=&geometryType=esriGeometryEnvelope&inSR=&spatialRel=esriSpatialRelIntersects&resultType=none&distance=0.0&units=esriSRUnit_Meter&returnGeodetic=false&outFields=SEG_ID&returnGeometry=true&featureEncoding=esriDefault&multipatchOption=none&maxAllowableOffset=&geometryPrecision=&outSR=4326&datumTransformation=&applyVCSProjection=false&returnIdsOnly=false&returnUniqueIdsOnly=false&returnCountOnly=false&returnExtentOnly=false&returnQueryGeometry=false&returnDistinctValues=false&cacheHint=false&orderByFields=&groupByFieldsForStatistics=&outStatistics=&having=&resultOffset=&resultRecordCount=&returnZ=false&returnM=false&returnExceededLimitFeatures=true&quantizationParameters=&sqlFormat=standard&f=pgeojson&token='
var cityStreets_721k_900k = 'https://services.arcgis.com/fLeGjb7u4uXqeF9q/arcgis/rest/services/Street_Centerline/FeatureServer/0/query?where=SEG_ID+%3E%3D++721000+AND+SEG_ID+%3C+900000&objectIds=&time=&geometry=&geometryType=esriGeometryEnvelope&inSR=&spatialRel=esriSpatialRelIntersects&resultType=none&distance=0.0&units=esriSRUnit_Meter&returnGeodetic=false&outFields=SEG_ID&returnGeometry=true&featureEncoding=esriDefault&multipatchOption=none&maxAllowableOffset=&geometryPrecision=&outSR=4326&datumTransformation=&applyVCSProjection=false&returnIdsOnly=false&returnUniqueIdsOnly=false&returnCountOnly=false&returnExtentOnly=false&returnQueryGeometry=false&returnDistinctValues=false&cacheHint=false&orderByFields=&groupByFieldsForStatistics=&outStatistics=&having=&resultOffset=&resultRecordCount=&returnZ=false&returnM=false&returnExceededLimitFeatures=true&quantizationParameters=&sqlFormat=standard&f=pgeojson&token='
var cityStreets_900k_ = 'https://services.arcgis.com/fLeGjb7u4uXqeF9q/arcgis/rest/services/Street_Centerline/FeatureServer/0/query?where=SEG_ID+%3E%3D++900000+&objectIds=&time=&geometry=&geometryType=esriGeometryEnvelope&inSR=&spatialRel=esriSpatialRelIntersects&resultType=none&distance=0.0&units=esriSRUnit_Meter&returnGeodetic=false&outFields=SEG_ID&returnGeometry=true&featureEncoding=esriDefault&multipatchOption=none&maxAllowableOffset=&geometryPrecision=&outSR=4326&datumTransformation=&applyVCSProjection=false&returnIdsOnly=false&returnUniqueIdsOnly=false&returnCountOnly=false&returnExtentOnly=false&returnQueryGeometry=false&returnDistinctValues=false&cacheHint=false&orderByFields=&groupByFieldsForStatistics=&outStatistics=&having=&resultOffset=&resultRecordCount=&returnZ=false&returnM=false&returnExceededLimitFeatures=true&quantizationParameters=&sqlFormat=standard&f=pgeojson&token='


export default {

  methods: {
    initMap() {

        mapboxgl.accessToken = 'pk.eyJ1IjoiYWtzaGF5N2luMiIsImEiOiJjam1xY3dwd24xb2w0M3BtajloNm01ZnZ1In0.lN36aIIC81PO2KGqyaoB-A';
        var map = new mapboxgl.Map({
            container: 'map',
            style: 'mapbox://styles/mapbox/light-v10',
            center: [-75.1652, 39.9526],
            zoom: 11
        }); 

        map.addSource("set-1", {
          "type": "geojson",
          "data": cityStreets_0_401k
        });

        
        // map.addSource("set-2", {
        //   "type": "geojson",
        //   "data": cityStreets_401k_541k
        // });

        
        // map.addSource("set-3", {
        //   "type": "geojson",
        //   "data": cityStreets_541k_721k
        // });

        
        // map.addSource("set-4", {
        //   "type": "geojson",
        //   "data": cityStreets_721k_900k
        // });

        
        // map.addSource("set-5", {
        //   "type": "geojson",
        //   "data": cityStreets_900k_
        // });   
        
        map.on('load', function () {
        
              map.addLayer({
                  "id": "streets-1",
                  "type": "line",
                  "source": {
                    "type": "geojson",
                    "data": 'set-1'
                  },
                  "layout": {
                    "line-join": "round",
                    "line-cap": "round"
                    },
                  "paint": {
                    "line-color": "#fc3003",
                    "line-width": 1
                    }
              });

              // map.addLayer({
              //   "id": "streets-1",
              //   "type": "line",
              //   "source": {
              //     "type": "geojson",
              //     "data": 'set-2'
              //   },
              //   "layout": {
              //     "line-join": "round",
              //     "line-cap": "round"
              //     },
              //   "paint": {
              //     "line-color": "#fc3003",
              //     "line-width": 1
              //     }
              // });
          
              // map.addLayer({
              //   "id": "streets-1",
              //   "type": "line",
              //   "source": {
              //     "type": "geojson",
              //     "data": 'set-3'
              //   },
              //   "layout": {
              //     "line-join": "round",
              //     "line-cap": "round"
              //     },
              //   "paint": {
              //     "line-color": "#fc3003",
              //     "line-width": 1
              //     }
              // });

              // map.addLayer({
              //   "id": "streets-1",
              //   "type": "line",
              //   "source": {
              //     "type": "geojson",
              //     "data": 'set-4'
              //   },
              //   "layout": {
              //     "line-join": "round",
              //     "line-cap": "round"
              //     },
              //   "paint": {
              //     "line-color": "#fc3003",
              //     "line-width": 1
              //     }
              // });

              // map.addLayer({
              //   "id": "streets-1",
              //   "type": "line",
              //   "source": {
              //     "type": "geojson",
              //     "data": 'set-'
              //   },
              //   "layout": {
              //     "line-join": "round",
              //     "line-cap": "round"
              //     },
              //   "paint": {
              //     "line-color": "#fc3003",
              //     "line-width": 1
              //     }
              // });
            }); 
        }  
  },
 
  mounted: function() {
    this.initMap()
  }
}

</script>


