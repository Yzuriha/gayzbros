<template>
  <observer :once="true" @intersect="showSection = true"></observer>
  <h3-headline :headline-title="categoryTitle"></h3-headline>
  <div v-show="showSection" class="karte-category">
    <karte-card v-for="item in items"
                :art="art"
                :img-link="item.img"
                :name="item.name"
                :preis="item.preis">
    </karte-card>
  </div>
</template>

<script>
import H3Headline from "@/components/headline/h3-headline.vue";
import KarteCard from "@/components/cards/karte-card.vue";
import Observer from "@/components/sections/observer.vue";

export default {
  components: {Observer, KarteCard, H3Headline},
  props: {
    categoryTitle: String,
    items: Array,
    art: String,
  },
  data() {
    return {
      showSection: false
    }
  }
}

</script>
