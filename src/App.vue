<template>
  <h1>IdeaBox</h1>
  <Ideas @delete = "deleteIdea" :ideaList = "ideaList"/>
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
    }
  },
  methods:{
    addIdea(idea){
      if(!this.ideaList.includes(idea) && idea){
        this.ideaList.push(idea)
      }
    },
    deleteIdea(idea){
      this.ideaList.splice(this.ideaList.indexOf(idea),1)
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
