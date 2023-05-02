<script>
import HeaderSection from './components/Header/Header.vue'
import MainSection from './components/Main/Main.vue'
import FooterSection from './components/Footer/Footer.vue'
export default {
  name: 'App',
  components: {
    HeaderSection, MainSection, FooterSection
  }
}
</script>

<template>
  <HeaderSection />
  <MainSection />
  <FooterSection />
</template>

<style lang="scss">

</style>
