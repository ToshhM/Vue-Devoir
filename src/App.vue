<template>
<div> 
  <navbar
     @change-component="changeSelectedComponent">
  </navbar>
 
  <keep-alive include="cours-view">
  <component :is="selectedComponent"
  v-bind="currentProps"
   @child-event="selectionUpdate"
  ></component>
  </keep-alive>
</div>
</template>

<script>
// changecomponent permet de switcher de composant en composant sans  router
import CoursView from './components/CoursView'
import SelectionCours from './components/SelectionCours'
import Navbar from './components/Navigation/Navbar'
export default {
  name: 'App',
  components: {
    CoursView, SelectionCours, Navbar
  },
 data(){
   return{
     selectedComponent:'cours-view',
     coursSelection:[]
   }
 },
 computed:{
   currentProps(){
   if(this.selectedComponent == "selection-cours"){
     return {selection : this.coursSelection} //probleme enlever this mettre cote
   }
   return false
   }
 },
 methods:{
    changeSelectedComponent(value) {
      this.selectedComponent = value
    },
    selectionUpdate(value) {
      this.coursSelection.push(value)
    }
 }
}
</script>

<style>

</style>