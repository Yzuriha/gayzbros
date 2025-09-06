<template>
  <div class="karte-card entrance-animation">
    <div class="karte-card__img">
      <base-image :img-src="imgSrc"></base-image>
    </div>
    <div class="karte-card__name-preis">
      <div class="karte-card__name">{{ name }}</div>
      <div class="karte-card__preis">{{ preis }}</div>
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
    art: String,
    imgLink: String
  },
  computed: {
    imgSrc() {
      //return `/src/assets/img/karte/${this.art}/${this.imgLink}`
      // Erstmal alles template, weil keine Bilder
      let random = Math.floor(Math.random() * (5 - 1 + 1) + 1);
      return `/img/template${random}.png`
    }
  }
}

</script>