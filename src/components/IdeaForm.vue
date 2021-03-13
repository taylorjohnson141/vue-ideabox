<template>
  <form @submit.prevent class = 'ideaForm' > 
    <input placeholder ='Add an Idea title!' v-model= 'idea' type="text">
    <input placeholder ='Add a Description!' v-model= 'description' type="text">
  </form>
  <button @click= "handleSubmit">Add Idea</button>
</template>

<script>
export default {
  data(){
    return {
      idea:'',
      description:'',
    }
  },
  methods:{
    handleSubmit(e){
      e.preventDefault()
      this.$emit("addIdea",this.idea,this.description)
      this.idea = ''
      this.description = ''
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