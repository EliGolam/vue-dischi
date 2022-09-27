<template>
  <main>
    <CardContainer class="cardContainer" :cards="cardsData" />
  </main>
</template>


<!-- SCRIPT -->
<script>
// Import Components
import CardContainer from '@/components/CardContainerComponent.vue';

export default {
    name: 'MainSection',

    props: {
        cardsData: Array,
    },

    
    components: {
        CardContainer,
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
}
</style>