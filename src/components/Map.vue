<template>
  <div>
    
    <div class="row map">
      <l-map :zoom="zoom" :center="center">
        <l-tile-layer :url="url" :attribution="attribution"></l-tile-layer>
        <l-marker v-for="(i, index) in BrewList" :key="index"
         :lat-lng="latlong(i.latitude, i.longitude)">

         </l-marker>
      </l-map>
    </div>
  </div>
</template>
<script>
import L from "leaflet";
import { LMap, LTileLayer, LMarker } from "vue2-leaflet";

export default {
  name: "Map",
  components: {
    LMap,
    LTileLayer,
    LMarker
  },
  props: {
    BrewList: Array
  },
  data: function() {
    return {
      zoom: 13,
      center: L.latLng(47.41322, -1.219482),
      url:
        "https://tile.thunderforest.com/transport/{z}/{x}/{y}.png?apikey=28264631cfeb4dd88a5f1132aece2291",
      attribution:
        '&copy; <a href="http://osm.org/copyright">OpenStreetMap</a> contributors',
      marker: L.latLng(47.41322, -1.219482)
    };
  },

  methods: {
    latlong(lat, lon){
        return L.latLng(lat, lon);
    }
  }
};
</script>
<style scoped>
.map {
  height: 95vh;
}
</style>