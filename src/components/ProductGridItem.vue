<script setup>
import { store } from '../data/store';
import { watch } from 'vue';

const filterByStock = () =>{
    if (store.filteredBy){
        return store.products.filter(x => x.isAvailable === true);
    } else {
        return store.products
    }
}

const filterByBrand = () => {
    if (store.checkedBrands.length!==0){
        return store.products.filter(el => store.checkedBrands.some(f => f === el.brand)); 
    }else{
        return store.products;
    }
}

const sortBy = (listOfProductsToSort) => {
    if (store.sortedBy==="priceAsc"){
        return listOfProductsToSort.sort((a, b) => (a.price > b.price ? 1 : -1));
    }else if(store.sortedBy==="priceDes"){
        return listOfProductsToSort.sort((a, b) => (a.price > b.price ? -1 : 1));
    }else if (store.sortedBy==="relevance"){
        const availableSorted = listOfProductsToSort.filter(x => x.isAvailable === true).sort((a, b) => (a.rank > b.rank ? 1 : -1));
        const unavailableSorted = listOfProductsToSort.filter(x => x.isAvailable === false).sort((a, b) => (a.rank > b.rank ? 1 : -1));
        return availableSorted.concat(unavailableSorted);
    }else{
        return listOfProductsToSort;
    }
}

const applyAllFiltersAndSort = () => {
    let filteredByBrand = filterByBrand();
    let filteredByStock = filterByStock();
    let filteredByBrandAndStock = filteredByBrand.filter(el => filteredByStock.some(f => f === el));
    let sortedProducts = sortBy(filteredByBrandAndStock);
    store.numOfProducts = sortedProducts.length;
    return sortedProducts;
}

watch(
    () => store.checkedBrands,
    () => {
        filterByBrand()
    }
)

watch(
    () => store.filteredBy,
    () => {
        filterByStock()
    }
)

</script>

<template>
    <main>
        <div class="grid-container">
            <div class="products" v-for="product in applyAllFiltersAndSort()" :key="product">
                <img class="image" :src=(product.image)>
                    <p class="prodtext">{{ product.name }}</p>
                    <p class="prodtext">{{ product.brand }}</p>
                    <p class="prodtext">£{{ product.price }}</p>
                </div>
        </div>
    </main>
</template>

<style scoped>
.grid-container {
	margin-left: 5%;
	margin-right: 5%;
	margin-top: 3%;
	margin-bottom: 3%;
	display: grid;
	grid-template-columns: repeat(auto-fit, minmax(300px, 3fr));
	grid-gap: 30px;
}

p{
    text-align: center;
    font-family: Arial, Helvetica, sans-serif;
	line-height: 0.5;
}

.image {
    width: 100%;
}

.products {
	font-size: 20px;
	border-radius: 10px;
	border-width: 5px;
	border-color: #000000;
	border-style: solid;
}

.products:hover {
    transform: scale(1.05);
}
</style>
