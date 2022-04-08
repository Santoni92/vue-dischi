<template>
  <main>
      <div class="container">
          <div v-if="albums.length > 0" class="album-gallery">    <!--sino a che il server non risponde restituendomi l'array di 10 elementi (vedi il console log) visualizzo il componente con il loader-->
          <!--sotto componente che mi serve per visualizzare il singolo album che compare nella galleria-->
            <MusicItem 
                v-for="(item,index) in albums"
                :key="index"
                :singleAlbum="item"
            />
          </div>
          <div v-else>
              <!--qui andrà il componente con il loader cosicchè mentre l'utente attende il risultato del server e quindi la visualizzazione degli elementi nella pagina verrà visualizzato un loader--->
          </div>
      </div>
  </main>
</template>

<script>
import axios from 'axios';  //prende il riferimento presente nella cartella node_modules (é questa l'istruzione per importare la libreria axios)
import MusicItem from '@/components/MusicItem.vue'

export default {
    name:'MusicList',
    data(){
        return{ albums:[]};
    },
    props:{
        url:String
    },
    mounted(){  // mounted() è la prima funzione che si avvia; mounted() lancia la funzione per far avviare il processo per prendere i dati dal server e passarli nei data del componente
        this.loadData();
    },
    methods:{
        loadData(){ //funzione per avviare la chiamata dell'api così da prendere gli elementi che mi servono e passarli ai data (cioè l'array albums)
            axios.get(this.url,true).then((response)=>{
                //console.log(response);
                const resultFromApi = response;
                console.log(resultFromApi); //stampa per vedere che tipo di struttura dati ottengo in risposta alla chiamata api 
                if(resultFromApi.status === 200) //check sullo status del server
                {
                    this.albums = resultFromApi.data.response;
                    console.log(this.albums[0]);
                }
            }).catch((err) => {
                console.log(err);
            });
        }
    },
    components:{
        MusicItem
    }
}
</script>

<style lang="scss" scoped> 
main{
    background-color: #1e2d3b;
    flex-grow:1;
    .container{
         max-width:1200px;
         margin:0 auto;
         .album-gallery{
             display:flex;
             flex-wrap:wrap;
         }
        }
}
     
</style>