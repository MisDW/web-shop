<template>
  <div class="product-card">
    <img class="img" :src="product.image" alt="Product image" />
    <div class="content-info">
      <!-- <p class="description">{{ product.description }}</p> -->
      <div class="price-rate">
        <p class="price">Price: ${{ product.price }}</p>
        <p class="rate">Rating: {{ product.rating.rate }}</p>
      </div>
      <button :id="product.id" class="btn btn-add">Añadir</button>
      <button :id="product.id" class="btn btn-buy">Comparar</button>
    </div>
    <slot></slot>
  </div>
</template>

<style scoped>

.product-card{
  max-width: 200px;
  height: fit-content;
  display: flex;
  flex-direction: column;
  gap: 10px;
  background-color: #f5f5f5;
  color: #000000;
  margin: 10px;
  border-radius: 10px;
  padding: 1rem;
  overflow: hidden;
}

.img{
  width: 100%;
  height: 180px;

}

.content-info{
  display: flex;
  flex-direction: column;
  gap: 20px;
}

.price-rate{
  display: flex;
  flex-direction: row;
  justify-content: space-between;
}

.description{
  height: 50px;
  overflow-y: scroll;
}

.btn{
  padding: 10px;
  border-radius: 10px;
  border: 0px;
  font-weight: bold;
}



</style>

<script setup>
  import { defineProps } from 'vue';

const props = defineProps({
  product: {
    type: Object,
    required: true
  }
});
</script>


