<template>
  <base-section headline-title="Karte" @headerClicked="detailAnsicht = !detailAnsicht">
    <template v-slot:titleExtra>
      {{ detailAnsicht ? '(zur Kurzansicht)' : '(zur Detailansicht)' }}
    </template>
    <div v-if="detailAnsicht" class="karte-section">
      <karte-category :items="KARTE_WARM" art="warm" category-title="warme Getränke"></karte-category>
      <karte-category :items="KARTE_KALT" art="kalt" category-title="eiskalt & Koffein"></karte-category>
      <karte-category :items="KARTE_SOFTDRINKS" art="softdrinks" category-title="Durstlöscher"></karte-category>
      <karte-category :items="KARTE_BIER" art="bier" category-title="Waldhaus Biere aus der Flasche"></karte-category>
      <karte-category :items="KARTE_WEIN" art="wein" category-title="Weingut Johler"></karte-category>
      <karte-category :items="KARTE_COCKTAILS" art="cocktails" category-title="Cocktails & Spritziges"></karte-category>
      <karte-category :items="KARTE_FOOD" art="food" category-title="Kuchen & Gebäck hausgemacht"></karte-category>
    </div>

    <div v-else class="karte-compact-section">
      <karte-category-compact :items="KARTE_WARM" art="warm" category-title="warme Getränke">
        <div>Ihr habt die Wahl zwischen Hafer- und Kuhmilch.</div>
        <div>Kaffeegetränke auch entkoffeiniert erhältlich +30 cent (außer Espresso)</div>
        <karte-card-compact-img img-src="img/karte/cafe.svg"
                                info="warm oder eiskalt genießen"
                                name="CÀ PHÊ SŨA DÁ"
                                preis="4.5 EURO">
        </karte-card-compact-img>
      </karte-category-compact>
      <karte-category-compact :items="KARTE_KALT" art="kalt"
                              category-title="eiskalt & Koffein"></karte-category-compact>
      <karte-category-compact :items="KARTE_SOFTDRINKS" art="softdrinks"
                              category-title="Durstlöscher"></karte-category-compact>
      <karte-category-compact :items="KARTE_BIER" art="bier"
                              category-title="Waldhaus Biere aus der Flasche"></karte-category-compact>
      <karte-category-compact :items="KARTE_WEIN" art="wein" category-title="Weingut Johler"></karte-category-compact>
      <karte-category-compact :items="KARTE_COCKTAILS" art="cocktails"
                              category-title="Cocktails & Spritziges">
        <karte-card-compact-img img-src="img/karte/martini.svg"
                                name="ESPRESSO MARTINI"
                                preis="9 EURO">
        </karte-card-compact-img>
      </karte-category-compact>
      <karte-category-compact :items="KARTE_FOOD" art="food"
                              category-title="Kuchen & Gebäck hausgemacht">
        <div>Weitere Auswahl an Kuchen und Gebäck findet Ihr an der Theke.</div>
      </karte-category-compact>
    </div>
    <div class="vegan-disclamer">
      <base-image img-src="img/karte/vegan.svg"></base-image>
      <div>Informationen über Zutaten in unseren Speisen, die
        <b>Allergien oder Unverträglichkeiten</b> auslösen können, erhalten Sie auf Nachfrage in unserer Allergenkarte
      </div>
    </div>
  </base-section>
</template>

<script>

import H2Headline from "@/components/headline/h2-headline.vue";
import KarteCategory from "@/components/sections/karte/karte-category.vue";
import {
  KARTE_BIER,
  KARTE_COCKTAILS,
  KARTE_FOOD,
  KARTE_KALT,
  KARTE_SOFTDRINKS,
  KARTE_WARM,
  KARTE_WEIN
} from "@/consts/karte.js";
import Observer from "@/components/sections/observer.vue";
import BaseSection from "@/components/sections/base-section.vue";
import KarteCategoryCompact from "@/components/sections/karte/karte-category-compact.vue";
import KarteCardCompactImg from "@/components/cards/karte-card-compact-img.vue";
import BaseImage from "@/components/images/base-image.vue";

export default {
  components: {BaseImage, KarteCardCompactImg, KarteCategoryCompact, BaseSection, Observer, KarteCategory, H2Headline},
  data() {
    return {
      detailAnsicht: false
    }
  },
  created() {
    this.KARTE_WARM = KARTE_WARM
    this.KARTE_KALT = KARTE_KALT
    this.KARTE_SOFTDRINKS = KARTE_SOFTDRINKS
    this.KARTE_BIER = KARTE_BIER
    this.KARTE_WEIN = KARTE_WEIN
    this.KARTE_COCKTAILS = KARTE_COCKTAILS
    this.KARTE_FOOD = KARTE_FOOD
  }

}
</script>

