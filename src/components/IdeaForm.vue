<template>
  <form @submit.prevent class = 'ideaForm' > 
    <input placeholder ='Add an Idea!' v-model= 'idea' type="text">
  </form>
  <button @click= "handleSubmit">Add Idea</button>
</template>

<script>
export default {
  data(){
    return {
      idea:''
    }
  },
  methods:{
    handleSubmit(e){
      e.preventDefault()
      this.$emit("addIdea",this.idea)
      this.idea = ''
    }
  }
}
</script>

<style>
.ideaForm{
  margin: 2px;
  display: inline;
}
</style>