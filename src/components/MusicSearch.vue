<template>
  <!--select @change="showLabelValue($event)">
      <option value="">All</option>
      <option value="rock">Rock</option>
      <option value="pop">Pop</option>
      <option value="jazz">Jazz</option>
      <option value="metal">Metal</option>
  </select-->
  <input type="text" placeholder="Cerca" v-model="inputText" @keyup.enter="$emit('search',inputText)">
</template>

<script>
export default {
    name:'MusicSearch',
    data(){
        return{
            //selectedLabel: '',
            inputText: ''
            }
    },
    methods:{
       /* showLabelValue(event){
            console.log(event.target.value);
            this.selectedLabel = event.target.value;
            this.$emit('search',this.selectedLabel);
        }*/
    }
}
</script>

<style>

</style>