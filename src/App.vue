<template>
  <loading-screen></loading-screen>
  <header-section></header-section>
  <main-section></main-section>
  <footer-section></footer-section>
</template>

<script>
import {defineComponent} from "vue";
import HeaderSection from "@/components/sections/header-section.vue";
import MainSection from "@/components/sections/main-section.vue";
import FooterSection from "@/components/sections/footer-section.vue";
import BaseSection from "@/components/sections/base-section.vue";
import LoadingScreen from "@/components/sections/loading-screen.vue";

export default defineComponent({
  components: {LoadingScreen, BaseSection, FooterSection, MainSection, HeaderSection}
})
</script>


<style lang="less">

@mobile-width: 500px;
@tablet-width: 750px;
@medium-width: 1000px;
@large-width: 1500px;

@primary-color: #69744E;
@default-color: #414141;

@default-margin: 3rem;


html {
  font-size: 10px;
}

body {
  margin: 0;
  font-family: 'Arial', 'Helvetica', sans-serif;
  color: @default-color;
  overflow-y: scroll; /* Show vertical scrollbar */
}

h1 {
  writing-mode: vertical-rl;
  text-orientation: upright;
  margin: @default-margin;
  font-size: 7rem;
  color: @primary-color;
}

h2 {
  font-size: 3.5rem;
  text-transform: uppercase;
  margin: 0;
  color: @primary-color;

  .h2-additional {
    font-size: 1.5rem;
    margin-left: 5px;
    cursor: pointer;
  }
}

h3 {
  font-size: 2.5rem;
  text-transform: uppercase;
  margin: 0;
}

header {
  height: 100vh;
  background: #B4B79AFF;
  background: linear-gradient(0deg, rgba(180, 183, 154, 0.35) 0%, rgba(255, 255, 255, 1) 100%);
  margin-bottom: 10rem;
  line-height: 1;

  .header-arrow {
    margin: 3rem;
    height: 7rem;
    width: 7rem;
    text-align: center;
    animation: upDown 2s ease-in-out infinite;

    img {
      height: 100%;
    }
  }

  .header-image {
    width: 100%;
    height: 95%;
    position: absolute;
    bottom: 0;
    display: flex;
    justify-content: flex-end;
    align-items: flex-end;
    @media (max-width: @medium-width) {
      height: initial;
    }

    img {
      height: 100%;
      @media (max-width: @large-width) {
        height: initial;
        width: 100%;

      }
    }

  }
}

main {
  margin: 0 auto;
  max-width: 1280px;
}

section {
  margin: 0 @default-margin;
  padding: 3rem 0;
}

hr {
  background-color: @primary-color;
  border: 0 none;
  color: @primary-color;
  height: 2px;
}

footer {
  display: flex;
  justify-content: center;
  gap: 1rem;
  font-size: 1.5rem;
  margin: 10px 0;
}

.event-card {
  font-size: 2rem;
  width: 100%;
  margin: 15px 0;

  display: flex;
  gap: 15px;
  align-items: center;

  .event-card__date-type {
    display: flex;
    align-items: center;
    gap: 15px;

    @media (max-width: @mobile-width) {
      display: grid;
      gap: 5px;
    }

    .event-card__date {
    }

    .event-card__type {
      height: 1.25rem;
      min-width: 10rem;
      border: 2px solid @primary-color;
      border-radius: 5px;
      text-align: center;
      text-transform: uppercase;
      font-size: 1rem;
      padding: 5px;
    }
  }


  .event-card__content {
    grid-area: content;
  }

  .event-card__link {
    grid-area: link;
  }

}

.karte-section {
  h3 {
    margin-top: 4rem;
    margin-bottom: 1rem;
  }

  .karte-category {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
    row-gap: 6rem;
    column-gap: 1.5rem;
    margin-bottom: 7rem;


    .karte-card {
      position: relative;

      .karte-card__name-preis {
        position: absolute;
        margin-top: -1.15rem;
        color: #414141;
        font-size: 2rem;
        text-align: end;
        right: 5px;

        .karte-card__name {
          font-weight: bold;
        }
      }

      img {
        width: 100%;
      }
    }

  }
}


.karte-compact-section {
  column-count: 3;
  column-gap: 5rem;
  margin-top: 4rem;

  @media (max-width: @tablet-width) {
    column-count: 2;
  }

  @media (max-width: @mobile-width) {
    column-count: 1;
  }


  .karte-compact-section-wrapper {
    break-inside: avoid;


    .karte-category-compact {
      margin-bottom: 3rem;
      margin-top: 1rem;

      .karte-card-compact {
        font-weight: lighter;
        display: block;
        font-size: 1.5rem;
        border-bottom: 1px solid @default-color;
        padding: 5px 0;

        .karte-card-compact__name-preis {
          width: 100%;
          display: flex;
          justify-content: space-between;
        }

        .karte-card-compact__info {
          opacity: 0.6;
          margin-top: 5px;
        }
      }

      .karte-category-compact__additional {
        font-size: 1.5rem;
        font-weight: bold;
        margin: 5px 0;
      }

    }

    .karte-card-compact-img {
      display: flex;
      margin: 5rem 0;
      gap: 5rem;
      align-items: center;
      font-weight: lighter;

      img {
        width: -webkit-fill-available;
      }

      .karte-card-compact-img__name {
        font-weight: bold;
      }

      .karte-card-compact-img__info {
        opacity: 0.6;
      }
    }
  }
}

.vegan-disclamer {
  display: flex;
  font-size: 1.5rem;
  margin-top: 5rem;
  align-items: center;
  gap: 1rem;

  img {
    height: 2rem;
  }
}

.gallery-container {
  column-count: 4;
  column-gap: 1rem;
  margin-top: 4rem;

  @media (max-width: @tablet-width) {
    column-count: 3;
  }

  @media (max-width: @mobile-width) {
    column-count: 2;
  }


  img {
    width: 100%;
    height: auto;
    margin-bottom: 1rem;
  }
}

@keyframes upDown {
  0%, 100% {
    transform: translateY(0);
  }
  50% {
    transform: translateY(-20px); /* adjust height */
  }
}

// Title Slide In
.title-animation-enter-active {
  animation: slide-in 1.5s;
}

.title-animation-leave-active {
  animation: slide-in 1.5s;
}

@keyframes slide-in {
  0% {
    transform: translateX(-40px);
    opacity: 0;
  }
  100% {
    transform: translateX(0px);
    opacity: 1;
  }
}

// Card Entrace Animation
.entrance-animation {
  animation: cardEntrance 700ms 0s ease-out;
  animation-fill-mode: backwards;
}


@keyframes cardEntrance {
  from {
    opacity: 0;
    transform: scale(0.9);
  }
  to {
    opacity: 1;
    transform: scale(1);
  }
}

// Standard Long Fade
.standard-long-fade-enter-active,
.standard-long-fade-leave-active {
  transition: opacity 1.5s ease;
}

.standard-long-fade-enter-from,
.standard-long-fade-leave-to {
  opacity: 0;
}


</style>
