<template>
  <div>
   
    <CharactersContainer></CharactersContainer>
   
  </div>
</template>

<script>
import CharactersContainer from "./components/CharactersContainer.vue";

export default {
  name: 'App',
  components:{
    CharactersContainer,
  }
  
}
</script>

<style lang="scss">
@import "@/styles/app";

</style>
