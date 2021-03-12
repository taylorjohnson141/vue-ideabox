<template>
  <div class = 'ideas'>
    <div  class = 'idea' v-for = "idea in ideaList" :key= "idea">
      <p>{{idea}}</p>
      <button @click= "removeIdea(idea)">Delete Idea</button>
    </div>
  </div>
</template>

<script>
export default {
  props:["ideaList"],
  methods:{
    removeIdea(idea){
      this.$emit('delete',idea)
    }
  }
}
</script>

<style>
.ideas{
  display: grid;
  gap: 2rem;
  grid-template-columns: 1fr 1fr 1fr;
  margin: 10px;
}
.idea{
  border: 1px blue solid;
  cursor: pointer;
}
</style>