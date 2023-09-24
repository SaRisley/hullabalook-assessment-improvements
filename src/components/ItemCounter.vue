<script setup>
import { store } from '../data/store';
</script>

<template>
    <p v-if="store.numOfProducts===0">
    {{ store.products.length }} items found</p>
    <p v-else>
    {{ store.numOfProducts }} items found</p>
</template>