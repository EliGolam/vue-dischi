<template>
  <article class="card">
    <div class="img-container">
      <img :src="imgSrc" alt="" @error="replaceErrorImg" />
    </div>

    <h3 class="fs-3">{{ title }}</h3>

    <div class="info fs-5 flex-wrap">
      <p class="author fs-4">{{ author }}</p>
      <p>{{ year }}</p>
      <p>{{ genre }}</p>
    </div>
  </article>
</template>


<!-- SCRIPT -->
<script>
import errorImg from '@/assets/logo.png'

export default {
    name: 'CardItem',

    props: {
        title: String,
        author: String,
        year: String,
        genre: String,
        imgSrc: String,
    },

    methods: {
      replaceErrorImg(e) {
        e.target.src = errorImg;
      }
    }
}
</script>


<!-- STYLE -->
<style lang="scss" scoped>
.card {
  padding: 1rem;
  text-align: center;
  transition: padding 200ms ease-in;
  cursor: pointer;

  .img-container {
  max-width: 100%;
  aspect-ratio: 1 / 1;
  
    img {
      width: 100%;
      height: 100%;
      object-fit: cover;
    }
  }

  .info {
    margin: 1em auto;
    justify-content: space-evenly;
    opacity: .5;
    transition: opacity 200ms ease-in;

    .author {
      width: 100%;
    }
  }

  &:hover {
    padding: .4rem;
    
    .info {
      opacity: .8;
    }
  }
}



</style>