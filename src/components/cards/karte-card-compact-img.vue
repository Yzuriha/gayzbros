<template>
  <div class="karte-card-compact-img">
    <base-image :img-src="imgSrc"></base-image>
    <div class="karte-card-compact-img__content">
      <div class="karte-card-compact-img__name">{{ name }}</div>
      <div class="karte-card-compact-img__preis">{{ preis }}</div>
      <div v-if="info?.length" class="karte-card-compact-img__info" v-html="info"></div>
    </div>
  </div>
</template>

<script>

import BaseImage from "@/components/images/base-image.vue";

export default {
  components: {BaseImage},
  props: {
    name: String,
    preis: String,
    info: String,
    imgSrc: String,
  },
  computed: {}
}

</script>