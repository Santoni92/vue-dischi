<template>
  <main>
      <div class="container">

      </div>
  </main>
</template>

<script>
import axios from 'axios';  //prende il riferimento presente nella cartella node_modules (é questa l'istruzione per importare la libreria axios)
export default {
    name:'MusicList',
    data(){
        return{ albums:[]};
    },
    props:{
        url:String
    },
    mounted(){
        this.loadData;
    },
    methods:{
        loadData(){
            axios.get('this.url',true).then((response)=>{
                console.log(response);
            })
        }
    }
}
</script>

<style lang="scss" scoped> 
main{
    
    .container{
         max-width:1200px;
         margin:0 auto;
        }
}
     
</style>