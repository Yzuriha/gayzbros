<template>
  <img :src="imgSrc" alt="" class="base-image" loading="lazy">
</template>

<script>
export default {
  props: {
    imgSrc: String
  }
}
</script>