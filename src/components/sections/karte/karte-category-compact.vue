<template>
  <observer :once="true" @intersect="showSection = true"></observer>

  <transition name="standard-long-fade">
    <div v-show="showSection" class="karte-compact-section-wrapper">
      <h3-headline :headline-title="categoryTitle"></h3-headline>
      <div class="karte-category-compact">
        <karte-card-compact v-for="item in items"
                            :info="item.info"
                            :is-vegan="item.vegan"
                            :name="item.name"
                            :preis="item.preis">
        </karte-card-compact>
        <div class="karte-category-compact__additional">
          <slot></slot>
        </div>
      </div>
    </div>
  </transition>
</template>

<script>

import {defineComponent} from "vue";
import Observer from "@/components/sections/observer.vue";
import H3Headline from "@/components/headline/h3-headline.vue";
import KarteCardCompact from "@/components/cards/karte-card-compact.vue";

export default defineComponent({
  components: {KarteCardCompact, H3Headline, Observer},
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
})
</script>
