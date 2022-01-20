<template>
<div>
   <h1 class="display-1">Commander</h1>

   <h2>Produits disponnibles</h2>

  <div class="card-deck">
    <produit v-for="produit in produits" role="commander" :nom="produit.nom" :prix="produit.prix" :key="produit" v-on:commande="ajoutProduit"/>
  </div>
  <h2>Produits commandés</h2>
  <div class="card-deck">
    <produit v-for="commande in commandes"  role="affichage" :key="commande" :nom="commande.nom" :prix="commande.prix"></produit>
  </div>
</div>
</template>

<script>
import Produit from "@/components/Produit.vue"

export default {
  data() {
    return {
      produits:[
          {nom:'Pizza', prix:3.0},
          {nom:'Frites', prix:2.0},
          {nom:'Hamburger', prix:2.5},
          {nom:'Cheeseburger', prix:3.0},
      ],
      commandes:[
        {nom:'Frites', prix:2.0}
      ]
    }
  },
  components :{
    Produit,
  },
  methods:{
    ajoutProduit(nom, prix) {


        this.commandes.push({nom:nom, prix:prix})


    }
  }
}
</script>

<style>

</style>
