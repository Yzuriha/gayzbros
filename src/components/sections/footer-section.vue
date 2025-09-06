<template>
  <footer>
    <div class="impressum" @click="showImpressum = true">
      Impressum
      <div v-if="showImpressum">
        <p>
          KorTraWi GmbH<br>
          Georg-Friedrich-StraÃŸe 34<br>
          76131 Karlsruhe<br>
          Deutschland
        </p>

        <p>
          Vertreten durch die GeschÃ¤ftsfÃ¼hrung:<br>
          Simon Korz, Trung Duc Tran, Marian Wilhelm
        </p>

        <b>Kontakt</b>

        E-Mail: info@dasgazebo.de<br>
        Website: https://dasgazebo.de

        <b>Registergericht</b>
        Amtsgericht Mannheim<br>
        Registernummer: HRB 749576

        <b>Umsatzsteuer</b>
        Umsatzsteuer-ID: DE366116088

      </div>
    </div>
    <div class="instagram">
      <a href="https://www.instagram.com/gazebo_karlsruhe/" target="_blank">
        <base-image img-src="img/instagram.svg" style="height: 2rem"></base-image>
      </a>
    </div>
    <div class="google">
      <a href="http://maps.app.goo.gl/EWmEWjGu4jgnn46h8" target="_blank">
        <base-image img-src="img/google.svg" style="height: 2rem"></base-image>
      </a>
    </div>
  </footer>
</template>

<script>
import BaseImage from "@/components/images/base-image.vue";

export default {
  components: {BaseImage},
  data() {
    return {
      showImpressum: false
    }
  }
}

</script>