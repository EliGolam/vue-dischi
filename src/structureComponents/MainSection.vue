<template>
  <main class="container">
    <SelectFilterComponent @filter="filterGenre" />
    <SearchBar @search="filterSongs"/>
    <CardContainer class="cardContainer" :cards="cardsToDisplay" />
  </main>
</template>


<!-- SCRIPT -->
<script>
// Import Components
import CardContainer from '@/components/CardContainerComponent.vue';
import SearchBar from '@/components/SearchBarComponent.vue';
import SelectFilterComponent from '@/components/SelectFilterComponent.vue';

export default {
    name: 'MainSection',

    props: {
        cardsData: Array,
    },

    data() {
      return {
        filterText: '',
        filterChoiceGenre: '',
      }
    },

    computed: {
      cardsToDisplay() {
        if (this.filterText === '' && this.chosenGenre === '') {
          return this.cardsData;
        }

        console.log("DEBUG - Received Search text in MainSection", this.filterText);
        const filteredArray = [];

        this.cardsData.forEach(card => {
          if(this.filterOptions(card)) {
            if (this.chosenGenre === card.genre) filteredArray.push(card);
          }
        });

        console.log("New Filtered Array", filteredArray);
        return filteredArray;
      }, 

      chosenGenre() {
        console.log("TEST GENRE FILTER Option", this.filterChoiceGenre);
        return this.filterChoiceGenre;
      }
    },

    methods: {
      filterSongs(searchText) {
        this.filterText = searchText;
      }, 

      filterGenre(option) {
        this.filterChoiceGenre = option;
      },

      filterOptions({author, title}) {
        const checkAuthor = author.toLowerCase().includes(this.filterText.toLowerCase().trim());
        const checkTitle = title.toLowerCase().includes(this.filterText.toLowerCase().trim());

        return (checkAuthor || checkTitle);
      }
    },  

    components: {
      CardContainer,
      SearchBar,
      SelectFilterComponent
    }
}
</script>


<!-- STYLE -->
<style lang="scss" scoped>
// Scoped Variables
$padding-y: 3rem;

main {
    padding: $padding-y 0;
    overflow: auto;

    .cardContainer {
      width: 100%;
    }
}
</style>