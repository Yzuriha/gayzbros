<template>
  <section class="base-section">
    <observer :once="true" @intersect="showTitle = true"></observer>
    <transition name="title-animation">
      <h2-headline v-show="showTitle" :headline-title="headlineTitle" @headerClicked="$emit('headerClicked')">
        <slot name="titleExtra"></slot>
      </h2-headline>
    </transition>
    <slot></slot>
  </section>
</template>

<script>

import {defineComponent} from "vue";
import Observer from "@/components/sections/observer.vue";
import H2Headline from "@/components/headline/h2-headline.vue";

export default defineComponent({
  components: {H2Headline, Observer},
  emits: ['headerClicked'],
  props: {
    headlineTitle: String
  },
  data() {
    return {
      showTitle: false
    }
  }
})
</script>
