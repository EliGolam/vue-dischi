<template>
  <article>
    <div class="img-container">
      <img :src="imgSrc" alt="" />
    </div>

    <h3>{{ title }}</h3>
    <p>{{ author }}</p>
    <p>{{ year }}</p>
    <p>{{ genre }}</p>
  </article>
</template>


<!-- SCRIPT -->
<script>
export default {
    name: 'CardItem',

    props: {
        title: String,
        author: String,
        year: String,
        genre: String,
        imgSrc: String,
    }
}
</script>


<!-- STYLE -->
<style lang="scss" scoped>
.img-container {
  max-width: 100%;
  aspect-ratio: 1 / 1;
  
  img {
    width: 100%;
    height: 100%;
    object-fit: cover;
  }
}

</style>