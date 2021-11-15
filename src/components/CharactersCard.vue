<template>
  <div>
     <div class="background-card">
        <img class="my-img" :src="poster" alt="...">
        <div class="my-card-body">
          <h3 class="text-center text-white text-uppercase">{{ title }}</h3>
          <div class="subtitle-container">
           <h5>{{ author }}</h5>
           <h5>{{ year }}</h5>
          </div>
        </div>
      </div>

  </div>
</template>

<script>
export default {
  name: "CharactersCard",
  props:{
    poster: String,
    title: String,
    author: String,
    year: String

  },
}
</script>

<style>
  .background-card{
    background-color: rgba(43,58,70,255);
    display: flex;
    flex-direction: column;
    min-height: 450px;
  }
  .my-img{
    padding: 20px;
  }

  .my-card-body{
    padding: 0 11px;
  }

  .subtitle-container{
    text-align: center;
    padding: 10px 0px;
  }



</style>