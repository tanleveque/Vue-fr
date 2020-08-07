// ./components/MenuItem.vue
<script>
export default {
  name: "MenuItem",
  props: ["name", "image", "inStock", "quantity", "addToShoppingCart"]
}

</script>
<template>
  <div>
    <div  class="menu-item">
      <img class="menu-item__image" :src="image.source" :alt="image.alt" />
      <div>
        <h3>{{ name }}</h3>
        <p v-if="inStock">En stock</p>
        <p v-else>En rupture de stock</p>
        <div>
          <label for="add-item-quantity">Quantité : {{ quantity }}</label>
          <input v-model.number="quantity" id="add-item-quantity" type="number" />
          <button @click="addToShoppingCart(quantity)">Ajouter au panier d'achat</button>
        </div>
      </div>
    </div>
  </div>
</template>

