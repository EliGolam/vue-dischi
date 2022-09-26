<template>
  <section class="cardContainer container flex-wrap">
    <CardItem v-for="card in cards" :key="card.title"
        :title="card.title"
        :author="card.author"
        :year="card.year"
        :genre="card.genre"
        :imgSrc="card.poster"
        class="cardItem"
    />
  </section>
</template>

<!-- SCRIPT -->
<script>
// Import Components
import CardItem from '@/components/CardComponent_CenteredDisplay.vue';

export default {
    name: 'CardContainer',

    props: {
        cards: Array,
    },

    created() {
        console.log('DEBUG CardContainer Data:', this.cards);
    },

    components: {
        CardItem,
    }
}
</script>


<!-- STYLE -->
<style lang="scss" scoped>
// Scoper Variables
$r-gap: 1rem;
$c-gap: 1rem;

.cardContainer {
    row-gap: $r-gap;
    column-gap: $c-gap;

    .cardItem {
        width: calc(100% / 5 - $r-gap);
    }
}

</style>