<script setup>
import { store } from '../data/store';
</script>

<template>
    <div class="toolbartext">
        <input 
            type="checkbox" 
            @change="store.filteredBy = !store.filteredBy" > 
        <label>In stock</label>
    </div>
</template>

<style>

input[type="checkbox"]{
	accent-color: black;
	cursor: pointer;
}
</style>