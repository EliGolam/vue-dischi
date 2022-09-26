<template>
  <section>
    <LoadingMessage />
    <LoadingFail />
  </section>
</template>

  
<!-- SCRIPT -->
<script>
import LoadingMessage from '@/components/LoadingMessageComponent.vue';
import LoadingFail from '@/components/LoadingFailComponent.vue';


export default {
    name: "LoadingSection",
    components: {
    LoadingMessage,
    LoadingFail,
}
}
</script>
  
  
<!-- STYLE -->
<style lang="scss" scoped>
  
</style>