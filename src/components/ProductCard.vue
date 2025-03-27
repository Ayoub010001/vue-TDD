<script setup>
 import { products } from '../../mock-data/products';
 const emit = defineEmits(['add-to-cart']);
 function  addToCart(product) {
    emit('add-to-cart', product);
}
</script>
<template>
    <div v-for="product in products" :key="product.id" class="product-card">
        <h2>{{ product.name }}</h2>
        <p>${{ product.price }}</p>
        <p>{{ product.rating }}</p>
        <ul>
            <li>
                <img :src="product.images[0]" alt="Product Image" class="product-image" />
            </li>
        </ul>
        <button @click="addToCart(product)">add to cart</button>
    </div>
</template>
