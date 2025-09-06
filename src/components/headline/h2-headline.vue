<template>
  <div>
    <h2 @click="$emit('headerClicked')">
      <span>{{ headlineTitle }}</span>
      <span class="h2-additional"><slot></slot></span>
    </h2>
    <hr>
  </div>
</template>

<script>
export default {
  props: {
    headlineTitle: String
  },
  emits: ['headerClicked']
}
</script>