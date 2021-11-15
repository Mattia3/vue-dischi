<template>
  <div>
    <div class="background-header"></div>
    <div class="container-background">
      <div class="container">
        <div class="row row-cols-md-5 g-4  py-5">
          <div class="col" v-for="(character, i) in characterList" :key="i">
            <CharactersCard 
              :poster="character.poster"
              :title="character.title"
              :author="character.author"
              :year="character.year"
            ></CharactersCard>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import axios from "axios";
import CharactersCard from "./CharactersCard.vue"

export default {
  name: "CharactersContainer",
  components:{
    CharactersCard,
  },
  data(){
    return{
      characterList: [],
    }
  },
  mounted(){
    axios.get("https://flynn.boolean.careers/exercises/api/array/music")
    .then(resp => {
      this.characterList.push(...resp.data.response)
     
    })
  }

}

</script>

<style  lang="scss">
  .background-header{
  background-color: rgba(43,58,70,255);
  height: 70px;
  }

  .container-background{
    background-color: rgba(25,45,59,255);
  }

  

</style>