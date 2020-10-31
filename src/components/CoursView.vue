<template>

<div class=flex>
  <div class="w-1/5 border m-4 p-4 flex justify-between border-black" >
    <div>
      <selection-square
        :selection="selection"
        @change-component="changeSelectedComponent"
      >
      </selection-square>
</div>
</div>
   <div class="w-4/5"> 
  <cours-card v-for="(cours,index) in matiere.cours"
   :key="index" 
   :cours="cours"
   @add-cours="addCoursToSelection">
   </cours-card>
   </div>
</div>

</template>

<script>
import coursData from '../data/cours.json'
import CoursCard from './CoursCard'
import SelectionSquare from './SelectionSquare'

export default {
    name:"cours-view",
    components:{
        CoursCard,
        SelectionSquare
    },
    data(){
    return{
      matiere:coursData,
      selection:[]
    }
  },
  methods: {
    addCoursToSelection(cours){
      console.log(cours);
      this.selection.push(cours)
      this.$emit('child-event', cours)
    }
  }
}
</script>

<style scoped>
	
</style>