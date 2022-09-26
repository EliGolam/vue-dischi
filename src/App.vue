<template>
  <div id="app">
    <HeaderSection />
      <!-- This section contains the spotify logo -->
      
    <LoadingSection />

    <MainSection :cardsData="musicData"/>
      <!-- This section contains:
        * A CardContainerComponent -->
  </div>
</template>

<script>
// Import Components
import HeaderSection from '@/structureComponents/HeaderSection.vue';
import MainSection from '@/structureComponents/MainSection.vue';
import LoadingSection from '@/structureComponents/LoadingSection.vue';

// Import Axios
import axios from 'axios'


export default {
  name: 'App',

  data() {
    return {
      BOOLEAN_API: 'https://flynn.boolean.careers/exercises/api/',
      MUSIC_ENDPOINT: 'array/music',
      musicData: [],
    }
  },

  created() {
    this.retrieveMusicData();
  },

  // METHODS
  methods: {
    retrieveMusicData() {
      axios
        .get(this.BOOLEAN_API + this.MUSIC_ENDPOINT)
        .then(({status, data}) => { this.processData(status, data); })
        .catch(error => { this.errorHandler(error) });
    },

    processData(status, data) {
      const {success, response} = data;
          // console.log('Axios Response LOG', status, success, response);

          if(status === 200 && success) {
            this.musicData = response;
          }
    },

    errorHandler(error) {
      console.warn("ERROR while loading:", error);
    }
  },

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
