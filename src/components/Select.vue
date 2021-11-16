<template>
  <select class="select" v-model="genereMusicale" @change="$emit('badgeClick', genereMusicale)">
    <option selected value="">Selezione un genere musicale</option>
    <option  v-for="element, i in arrayGeneri" :key="i" :value="element">{{ element }}</option>
  </select>
</template>

<script>

export default {
  name: "Select",
  data(){
   return{
     genereMusicale: []
    }
  },
  props:["arrayGeneri"],
} 
</script>

<style lang="scss">
.select{
  margin-top: 42px;
  padding: 10px;
  background-color: brown;
  border-radius: 10px;
  border-color: brown;
  color: white;
}

</style>