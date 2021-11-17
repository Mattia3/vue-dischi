<template>
  <div>
    <div class="background-header"></div>
    <div class="container-background text-center">
       <Select :arrayGeneri="arrayGeneri" @badgeClick="filterGenere" ></Select>
       
      <div class="container">
        <div class="row row-cols-md-5 g-4  py-5">
          <div class="col" v-for="(character, i) in funzione" :key="i">
            <CharactersCard 
              :poster="character.poster"
              :title="character.title"
              :author="character.author"
              :year="character.year"
              :genre="character.genre"
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
import Select from "./Select.vue"

export default {
  name: "CharactersContainer",
  components:{
    CharactersCard,
    Select,
  },
  data(){
    return{
      characterList: [],
      arrayGeneri: "",
      variabileFiltro: "",
    }
  },
  mounted(){
    axios.get("https://flynn.boolean.careers/exercises/api/array/music")
    .then(resp => {
      this.characterList.push(...resp.data.response)
    }),
     axios.get("https://flynn.boolean.careers/exercises/api/array/music")
    .then(resp => {
    let arr = "";
      arr=(resp.data.response.map(function (el) {return el.genre}))
      this.arrayGeneri=[...new Set(arr)]
    })
  },
  methods:{
    filterGenere(genereSelezionato){
      this.variabileFiltro = genereSelezionato
      console.log(genereSelezionato)
     
    },
  },

  computed: {
    funzione(){
       if(!this.variabileFiltro){
        return this.characterList
      }
        return this.characterList.filter((albulm) => {
        return albulm.genre === this.variabileFiltro
      })
    }
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
    height: 100vh;
  }
  
</style>