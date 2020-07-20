<template>
  <div class="container">
    <div class="row">
      <div class="col-12">
        <h1 class="text-center text-info">Breweries List</h1>
       <!--  <h2>{{msg}} - {{name}}</h2>   -->      
      </div>
    </div>
    <div class="row">
      <div class="col-6">       
        <BrewList :BrewList="brews"/>
      </div>
      <div class="col-6">
        <Map :BrewList="brews"/>
      </div>
    </div>
  </div>
</template>

<script>
import BrewList from '../components/BrewList'
import Map from '../components/Map';
import axios from "axios";
export default {
  name: "Brew",
  data: function(){
    return{
      brews:[]
    }
  },
  components: {
    BrewList,
    Map
  },
  mounted: function() {
    axios.get("https://api.openbrewerydb.org/breweries").then(r => {
      this.brews = r.data;      
    });
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss" scoped>
.brew-list{
  overflow-y: scroll;
  height: 96vh;
  li{
    &:hover{
      background-color: darkgray;
    }
  }
}
</style>
