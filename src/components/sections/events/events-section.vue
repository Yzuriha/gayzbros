<template>
  <base-section headline-title="Events">
    <event-card v-for="event in EVENTS" :content="event.content"
                :date="event.date"
                :link="event.link"
                :type="event.type">
    </event-card>
  </base-section>
</template>


<script>
import H2Headline from "@/components/headline/h2-headline.vue";
import {EVENTS} from "@/consts/events.js";
import EventCard from "@/components/cards/event-card.vue";
import Observer from "@/components/sections/observer.vue";
import BaseSection from "@/components/sections/base-section.vue";

export default {
  components: {BaseSection, Observer, EventCard, H2Headline},
  created() {
    this.EVENTS = EVENTS;
  }

}
</script>