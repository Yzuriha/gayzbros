<template>
  <div class="karte-card-compact">
    <div class="karte-card-compact__name-preis">
      <div class="karte-card-compact__name">
        {{ name }}
        <base-image v-if="isVegan" img-src="img/karte/vegan.svg"></base-image>
      </div>
      <div class="karte-card-compact__preis">{{ preis }}</div>
    </div>
    <div v-if="info?.length" class="karte-card-compact__info" v-html="info"></div>
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
    isVegan: Boolean
  },
  computed: {}
}

</script>