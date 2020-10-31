<template>
  <div class="bg-green-300 p2 text-center">
    <a href="#" @click="changeComponent('cours-view')">Tous les cours</a> | 
    <a href="#" @click="changeComponent('selection-cours')">Ma sélection</a>
  </div>
</template>

<script>
export default {
  name: "navbar",
  methods: {
    changeComponent(value) {
      this.$emit('change-component', value)
    }
  }
}
</script>

<style>

</style>