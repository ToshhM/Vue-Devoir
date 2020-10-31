<template>
  <div class="container w-4/5 mx-auto mt-4">
    <h1 class="text-lg font-bold">Ma sélection</h1>

    <div v-if="selection.length == 0 ">
      <p>Aucun cours sélectionné</p>
    </div>
  
    <div v-else>
      <div
        v-for=" cours in selection"
        :key="cours.name" 
        class="border border-black my-4 p-2"
      >
        <h3>{{ cours.name }} ({{ cours.heure }}) ({{ cours.salle }}) ({{ cours.professeur }}) </h3>
        
        
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'selection-cours',
 props:['selection'],

}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
