<template>
  <h1>IdeaBox</h1>
  <Ideas @complete= 'completeIdea' @delete = "deleteIdea" :ideaList = "ideaList"/>
  <IdeaForm @addIdea = "addIdea"/>
</template>

<script>

import Ideas from  './components/Ideas'
import IdeaForm from './components/IdeaForm'

export default {
  name: 'App',
  components: {
    Ideas, IdeaForm
  },
  data(){
    return{
      ideaList:[],
      currentId : 0,
    }
  },
  methods:{
    addIdea(idea,description){
      if(!this.ideaList.includes(idea) && idea){
        this.ideaList.push({title:idea,description:description,isComplete:false,currentId:this.currentId})
        this.currentId ++
      }
    },
    deleteIdea(idea){
        this.ideaList = this.ideaList.filter((currentIdea) =>{
        return currentIdea.currentId !== idea.currentId
      })
    },
    completeIdea(idea){

      let currentIdea = this.ideaList.find((currentIdea) =>{
         return currentIdea.currentId === idea.currentId
      })
      currentIdea.isComplete = true
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
