<template>
  <div class = 'ideas'>
    <div  :class = "{ complete: idea.isComplete, idea }" v-for = "idea in ideaList" :key= "idea">
      <p>{{idea.title}}</p>
      <p>{{idea.description}}</p>
      <button @click= "removeIdea(idea)">Delete Idea</button>
      <button @click= "completeIdea(idea)">Complete idea</button>
    </div>
  </div>
</template>

<script>
export default {
  props:["ideaList"],
  methods:{
    removeIdea(idea){
      this.$emit('delete',idea)
    },
     completeIdea(idea){
      this.$emit('complete',idea)
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
.complete{
    text-decoration: line-through;
}
</style>