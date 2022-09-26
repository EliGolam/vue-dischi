<template>
  <div id="app">
    <HeaderSection />
      <!-- This section contains the spotify logo -->
      
    <LoadingSection />

    <MainSection />
      <!-- This section contains:
        * A CardContainerComponent -->
  </div>
</template>

<script>
// Import Components
import HeaderSection from '@/structureComponents/HeaderSection.vue';
import MainSection from '@/structureComponents/MainSection.vue';
import LoadingSection from '@/structureComponents/LoadingSection.vue';



export default {
  name: 'App',
  components: {
    HeaderSection,
    MainSection,
    LoadingSection
}
}
</script>

<style lang="scss">
@import '@/assets/styles/style.scss';

</style>
