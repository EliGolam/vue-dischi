<template>
  <main>
    <CardContainer :cards="cardsData" />
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

</style>