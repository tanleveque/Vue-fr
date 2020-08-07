<template>
  <div>
    <div v-for="item in simpleMenu" :key="item.name" class="menu-item">
      <img class="menu-item__image" :src="item.image.source" :alt="item.image.alt" />
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

// ./components/MenuItem.vue
<script>
export default {
  name: "MenuItem",
  props: ["name", "image", "inStock", "quantity"],
};
</script>



<style lang="scss">
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>