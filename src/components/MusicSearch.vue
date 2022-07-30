<template>
  <!--select @change="showLabelValue($event)">
      <option value="">All</option>
      <option value="rock">Rock</option>
      <option value="pop">Pop</option>
      <option value="jazz">Jazz</option>
      <option value="metal">Metal</option>
  </select-->
  <!--input type="text" placeholder="Cerca" v-model="inputText" @keyup.enter="$emit('search',inputText)"-->
  <div>
    <select v-model="selectedCategory" @change="changeCategory">
        <option value="">All categories</option>
        <option v-for="category in categories" :key="category" :value="category">{{category}}</option>
    </select>
  </div>
</template>

<script>
export default {
    name:'MusicSearch',
    data(){
        return{
            selectedCategory: '',
            }
    },
    props:{
        categories:Array
    },
    methods:{/*
        showLabelValue(event){
            console.log(event.target.value);
            this.selectedLabel = event.target.value;
            this.$emit('search',this.selectedLabel);
        }*/
        changeCategory(){
            console.log(this.selectedCategory);
            this.$emit('changedCategories', this.selectedCategory);
        }

    }
}
</script>

<style>

</style>