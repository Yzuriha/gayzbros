<template>
  <observer :once="true" @intersect="showSection = true"></observer>

  <transition name="standard-long-fade">
    <div v-show="showSection" class="event-card">
      <div class="event-card__date-type">
        <div class="event-card__date">{{ date }}</div>
        <div class="event-card__type">{{ type }}</div>
      </div>
      <div class="event-card__content">{{ content }}</div>
    </div>
  </transition>
</template>

<script>

import Observer from "@/components/sections/observer.vue";

export default {
  components: {Observer},
  props: {
    date: String,
    type: String,
    content: String,
    link: String,
  },
  data() {
    return {
      showSection: false
    }
  }
}
</script>
