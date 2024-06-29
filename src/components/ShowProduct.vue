<template>
    <ProductItem v-for="item in products" :key="item.id" :product="item"></ProductItem>
</template>

<script setup>
import ProductItem from "./ProductItem.vue";
import axios from 'axios'
import { ref, onMounted  } from 'vue';

let products = ref([]);
let cant = ref(5);

  async function getProducts() {
    return await axios.get(`https://fakestoreapi.com/products?limit=${cant.value}`).then( ( response ) => {
      try{
          const productArray = response.data;

          productArray.forEach((productData) => {
            const { id, category, description, image, price, rating, title } = productData;
            let product = {
            id: id,
            title: title,
            description: description,
            image: image,
            price: price,
            rating: rating,
            category: category
          }
            products.value.push(product);
          });

        } catch (err) {
        console.error("Error fetching product:", err);
      }
    }
  )
  }

onMounted(() => {
  getProducts();
});

</script>
