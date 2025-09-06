<template>
  <base-section headline-title="Galerie">
    <div class="gallery-container">
      <base-image v-for="img in GALLERY_IMAGES" :img-src="'img/gallery/' + img.src"></base-image>
    </div>
  </base-section>
</template>

<script>
import BaseSection from "@/components/sections/base-section.vue";
import {GALLERY_IMAGES} from "@/consts/gallery.js";
import BaseImage from "@/components/images/base-image.vue";

export default {
  components: {BaseImage, BaseSection},
  created() {
    this.GALLERY_IMAGES = GALLERY_IMAGES;
  }

}
</script>
