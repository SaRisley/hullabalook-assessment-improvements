<script setup>
import { store } from '../data/store';

const brandList = store.products.map(a => a.brand)

const noRepeatBrands = brandList.filter((item,index) => brandList.indexOf(item) === index);

</script>

<template>
    <div class="dropdown">
        <p>Brands</p>
        <div class="dropdown-content">
            <li class="brandsList" v-for="brand in noRepeatBrands" :key="brand">
                <input 
                    class="brandscheck"
                    type="checkbox" 
                    :value="brand"     
                    id="product.brand" 
                    v-model="store.checkedBrands" > 
                <label>{{ brand }}</label>
            </li>
        </div>
    </div>
</template>

<style>
.dropdown {
	position: relative;
	display: inline-block;
	text-align: left;
	color: black;
}

.dropdown-content {
	display: none;
	position: absolute;
	background-color: whitesmoke;
	min-width: 160px;
	box-shadow: 0px 8px 16px 0px rgba(0,0,0,0.2);
	padding: 12px 16px;
	z-index: 1;
	border-width: 5px;
	border-color: #fff;
	border-style: solid;
}

.dropdown:hover .dropdown-content {
	display: block;
	border-radius: 10px;
}

li {
	position: relative;
	display: inline-block;
	padding-right: 30px;
	color: black;
	text-align: center;
	font-family: Arial, Helvetica, sans-serif;
}


li :hover {
	background-color: whitesmoke;
	border-radius: 10px;
}

input[type="checkbox"]{
	accent-color: black;
	cursor: pointer;
}

</style>