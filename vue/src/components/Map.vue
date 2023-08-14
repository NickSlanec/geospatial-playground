<template>
  <div>
    <div ref="mapContainer" class="map-container min-h-screen"></div>
  </div>
</template>

<script>
import mapboxgl from 'mapbox-gl';

export default {
  name: 'Map',
  mounted() {
    this.initializeMap();
  },
  methods: {
    initializeMap() {
      mapboxgl.accessToken = '';
      const map = new mapboxgl.Map({
        container: this.$refs.mapContainer,
        style: 'mapbox://styles/mapbox/streets-v12', // style URL
        center: [-74.5, 40], // starting position [lng, lat]
        zoom: 9, // starting zoom
      });

      map.on('load', () => {
        map.addSource('radar', {
          'type': 'raster',
          'url': '../../element84_assignments/data/ndvi/1km/normalized_data-warped.tif',
        });
        map.addLayer({
          id: 'radar-layer',
          'type': 'raster',
          'source': 'radar',
          'paint': {
            'raster-fade-duration': 0
          }
        });
      });
    },
  },
};
</script>

<style scoped>
.map-container {
  width: 100%;
}
</style>
