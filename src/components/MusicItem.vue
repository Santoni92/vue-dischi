<template>
  <div class="card">
      <img :src="singleAlbum.poster" alt="">
      <div class="title">
          <span>{{singleAlbum.title}}</span>
      </div>
      <div class="author-year">
          <span>{{singleAlbum.author}}</span>
          <span>{{singleAlbum.year}}</span>
      </div>
  </div>
</template>

<script>
/* modello dati del singolo oggetto di cui è composto l'array di oggetti che ottengo in risposta alla chiamata api
author: "Bon Jovi"
genre: "Rock"
poster: "https://www.onstageweb.com/wp-content/uploads/2018/09/bon-jovi-new-jersey.jpg"
title: "New Jersey"
year: "1988"*/
export default {
    name:'MusicItem',
    props:{
        singleAlbum:Object
    }
}
</script>

<style lang="scss" scoped>
.card{
    width:calc(100% / 5);
    display:flex;
    flex-direction:column;
    background-color:#2e3a46 ;
    img{
        width:100%;
        margin-bottom:10px;
    }
    .title{
        display: flex;
        flex-direction:column;
        margin-bottom:20px;
        text-align:center;
        color:white;
        text-transform: uppercase;
    }
    .author-year{
         display: flex;
        flex-direction:column;
        align-items:center;
        color:#808077;
    }
}

</style>





