<template>

<div class="border-black border m-2 p-2 flex justify-between" 
:class="DisponibleStyle">  <!--On peut mettre plusieurs class , -->
  <h1 class="text-lg font-bold">{{ cours.name }} </h1>
  <p> {{cours.heure }} </p>
  <p> {{cours.professeur }} </p>
  <p> {{cours.salle }} </p>
  
    <base-button :disabled="false" :class="DisponibleStyle" text="Sélectionner" @click="addToSelection "></base-button> 
</div>

</template>

<script>


export default {
    name: "cours-card",
    props:['cours'],
    computed:{
      isDisponible()
        {
        if(this.cours.disponible =="absent"){ //if Disabled affiché un style diférents
            
            return true
        }
        return false
        },
    DisponibleStyle(){ // bind = liaison javascript
        return{
            'bg-gray-600': this.isDisponible,
            'bg-gray-white': this.isDisponible,
            'bg-gray-black': this.isDisponible,
             
            }
        }
    },
    DisabledButton(){
        
    },
    methods: {
        addToSelection(){
            this.$emit('add-cours', this.cours)

        }
    }
}

/*    
J'ai essayé de désactivé le bouton, lorsqu'on, on utilisant de la data mais cela fonctionne pas
data:()=>{
        return{
    isActive: true,

        }*/
</script>

<style>

</style>

