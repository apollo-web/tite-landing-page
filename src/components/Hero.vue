<template lang="pug">
  div#hero
    div.hero__dim
      div.container
        div.hero__container
          h1.hero__container--text
            | {{ serviceKo }}, {{ serviceEn }}
          h3.hero__container--subtext
            | {{ $t('generic.tagline') }}

        button.hero__scrolldown(
          v-scroll-to="{el: '#service', duration: 0, offset: -56}"
        )
          i.fa.fa-angle-down
</template>

<script>
import {globalVar} from '@/globalVar'

export default {
  name: 'hero',

  data () {
    return {
      serviceKo: globalVar.serviceKo,
      serviceEn: globalVar.serviceEn,
    }
  },

}
</script>

<style lang="scss">
$baseURI: '/src/assets/dist/hero.jpg';

#hero {
  width: 100%;
  background-image: url('#{$baseURI}');
  background-size: cover;
  background-repeat: no-repeat;
  background-position: center center;

  .hero__dim {
    height: 560px;
    position: relative;
    background-color: $black54;
    max-height: calc(96vh - #{$grid16x});

    .hero__container {
      top: 50%;
      left: 50%;
      color: #fff;
      text-align: center;
      position: absolute;
      margin-right: -50%;
      @include transform(translate(-50%, -50%));

      .hero__container--text {
        font-weight: 900;

        @media #{$pablet} {
          @include font-size($grid8x);
        }
      }

      .hero__container--subtext {
        font-weight: 400;
        margin-top: -#{$grid6x};
      }
    }

    .hero__scrolldown {
      left: 50%;
      color: #fff;
      bottom: $grid8x;
      width: $grid12x;
      height: $grid12x;
      border: 1px solid #fff;
      transition: all .25s ease;
      position: absolute !important;
      display: inline-block !important;
      @include border-radius($grid12x);
      @include transform(translateX(-50%));

      &:hover {
        background-color: $brand;
        border: 1px solid transparent;
      }

      .fa-angle-down {
        @include font-size($grid6x);
      }
    }
  }
}
</style>
