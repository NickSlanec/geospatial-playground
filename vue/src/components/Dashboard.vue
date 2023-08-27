<template>
  <div class="min-h-screen flex relative lg:static surface-ground">
    <div class="min-h-screen flex flex-column relative flex-auto">
      <div class="flex flex-column flex-auto min-h-screen">
        <Map/>
      </div>
    </div>
  </div>
</template>

<script>
import Map from './Map.vue'
export default {
  components: { Map },
  data() {
    return{
      activeTab: 0
    }
  }
}
</script>

<style></style>