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
        <h3>{{ item.name }}</h3>
        <p v-if="item.inStock">En stock</p>
        <p v-else>En rupture de stock</p>
        <div>
          <label for="add-item-quantity">Quantité : {{ item.quantity }}</label>
          <input v-model.number="item.quantity" id="add-item-quantity" type="number" />
          <button @click="addToShoppingCart(item.quantity)">Ajouter au panier d'achat</button>
        </div>
      </div>
    </div>
  </div>
</template>

