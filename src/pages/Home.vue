<template lang="pug">
  div#home
    Header
    Hero
    Service.section__each
    Information.section__each
    Download.section__each
    Mission.section__each
    Footer
    Kakao
</template>

<script>
import Header from '@/components/Header'
import Hero from '@/components/Hero'
import Service from '@/components/Service'
import Information from '@/components/Information'
import Download from '@/components/Download'
import Mission from '@/components/Mission'
import Footer from '@/components/Footer'
import Kakao from '@/components/misc/Kakao'

export default {
  name: 'home',

  data () {
    return {

    }
  },

  components: {
    Header,
    Hero,
    Service,
    Information,
    Download,
    Mission,
    Footer,
    Kakao
  },

}
</script>

<style lang="scss">
#hero {
  margin-top: $grid14x;
}

.section__each {
  padding: $grid16x 0 $grid20x;
}
</style>
