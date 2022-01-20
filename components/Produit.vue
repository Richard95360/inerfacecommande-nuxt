<template>
  <div  class="card text-white bg-dark mb-3" style="max-width: 18rem;">
    <div class="card-header"> {{ nom }}</div>
    <div class="card-body">
      <p class="card-text">Prix : {{ prix }}</p>
      <hr>
      <button v-if="role === 'commander'" class="btn btn-success" @click="$emit('commande', nom,prix)">commander!</button>
    </div>
  </div>
</template>

<script>
export default {
   name:'Produit',
   props: ["nom", "prix", "role"]
}
</script>

<style>

</style>
