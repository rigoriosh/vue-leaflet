<template>
  <div class="card brew-list">      
    <ul class="list-group list-group-flush">
      <li
        v-for="(i, index) in BrewList"
        v-bind:key="i.id"
        class="list-group-item"
      >{{index}} - {{i.name}}, {{i.state}}</li>
    </ul>
  </div>
</template>

<script>

export default {
  name: "BrewList",
  data: function() {
    return {
      brews: []
    };
  },
  props: {
    BrewList: Array
  },
  mounted: function() {
    this.brews = this.BrewList;
  }
};
</script>