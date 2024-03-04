<script setup lang="ts">
import { ref } from 'vue';
import { type Products ,getProducts} from "@/model/products";

const products = ref([] as Products[])
products.value = getProducts()
</script>

<template>
    <div class="product-list">
        <div v-for="products in products": key="products.id" class="card">
        <div class="card-image">
      <img :src="products.thumbnail" : alt="product.title"/>
        </div>
        <div class="card-content">
            <div class="media">
                <div class="media-content">
                    <p class="title is-4">{{products.title}}</p>
                    <p class="subtitle is-6">{{products.price}}</p>
                </div>
            </div>
            <div class="content">
                {{products.description}}
            </div>
    </div>
</template>

<style scoped>
.product-list {
    display: flex;
    flex-wrap: wrap;
    justify-content: space-around;
}
.card {
    flex-basis: 15rem;
    flex-grow: 1rem;
    max-width: .5rem;
}
h3{
    font-weight:bold;
}
.price{
    font-weight: bold;
    font-size: xx-large;
    color: pink;
    float:right;
}
</style>