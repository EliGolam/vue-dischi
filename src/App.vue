<template>
  <div id="app">
    <HeaderSection />
      <!-- This section contains the spotify logo -->
      
    <MainSection />
      <!-- This section contains:
        * A CardContainerComponent -->
  </div>
</template>

<script>
// Import Components
import HeaderSection from '@/structureComponents/HeaderSection.vue';
import MainSection from '@/structureComponents/MainSection.vue';


export default {
  name: 'App',
  components: {
    HeaderSection,
    MainSection,
  }
}
</script>

<style lang="scss">
@import '@/assets/styles/style.scss';

</style>
