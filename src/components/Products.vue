<template>
  <div>
    <h1>Products</h1>
    <div class="products">
      <div v-for="(product, index) in products" :key="index">
        <h3>{{product.name}}</h3>
        <div class="cost">{{product.cost}}</div>
        <img :src="product.image" width="500" height="600"/>
        <button v-on:click="addItemToCart(product)">Add to cart</button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data: () => {
    return {
      products: [
        {
          name: "Ekran kartı",
          cost: "₺25.877",
          image:"https://cdn.vatanbilgisayar.com/Upload/PRODUCT/msi/thumb/109368_large.jpg"
            
        },
        {
          name: "İşlemci",
          cost: "₺3.514",
          image:"https://productimages.hepsiburada.net/s/22/375/9988761485362.jpg"
            
        }
      ]
    };
  },
  methods: {
    addItemToCart(product) {
      this.$emit("addItemToCart", product);
    }
  }
};
</script>

<style>
</style>