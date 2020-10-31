<template>
  <div> Selection : {{selection.length}} 
      <span v-if="SelectionCours">Cours</span>
      <span v-else> cours</span>
      <ul>
      <li v-for="(cours, index) in selection" :key="index">{{ cours.name }} {{cours.professeur}} {{ cours.salle }}</li>
    </ul>

  </div>
</template>

<script>
export default {
    name:"selection-square",
    props: ['selection'], 
    computed:{
        SelectionCours(){
            if(this.selection.length <2 ){
                return true
            }
            return false
        }
    }
}
</script>

<style>

</style>