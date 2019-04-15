<template>
  <div >
    <map
  id="map"
  longitude="113.324520"
  latitude="23.099994"
  scale="14"
  controls="{{controls}}"
  bindcontroltap="controltap"
  markers="{{markers}}"
  bindmarkertap="markertap"
  polyline="{{polyline}}"
  bindregionchange="regionchange"
  show-location
  style="width: 100%; height: 300px;"
></map>
  </div>
</template>

<script>
// Use Vuex
import store from './store'

export default {
  computed: {
    count () {
      return store.state.count
    }
  },
  methods: {
    increment () {
      store.commit('increment')
    },
    decrement () {
      store.commit('decrement')
    }
  }
}
</script>

<style>
.counter-warp {
  text-align: center;
  margin-top: 100px;
}
.home {
  display: inline-block;
  margin: 100px auto;
  padding: 5px 10px;
  color: blue;
  border: 1px solid blue;
}
</style>
