<template>
  <div id="app">
    <Header/>
    <MusicList :url="apiUrl"/>
  </div>
</template>

<script>
import Header from './components/Header.vue' //import Header from '@/components/Header.vue'
import MusicList from './components/MusicList.vue'
export default {
  name: 'App',
  components: {
    Header,
    MusicList
  },
  //data
  data(){
    return{
          apiUrl:'https://flynn.boolean.careers/exercises/api/array/music' //ritorno l'indirizzo dell'api come dato così da passarlo alla props del componente Header
        }
    }
  }

</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  /*text-align: center;*/
  color: #2c3e50;
  /*margin-top: 60px;*/
}
</style>
