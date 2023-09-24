<script setup>
import { store } from '../data/store';
</script>

<template>
    <div class="dropdown">
        <p>Sort by</p>
        <div class="dropdown-content">
            <button class="sortbtn" @click='store.sortedBy = "priceAsc"'>Price ascending</button>
            <br>
            <button class="sortbtn" @click='store.sortedBy = "priceDes"'>Price descending</button>
            <br>
            <button class="sortbtn" @click='store.sortedBy = "relevance"'>Relevance</button>
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

.sortbtn {
	background-color: rgb(255, 255, 255);
	border-radius: 6px;
	border-width: 1px;
	border-style: solid;
	border-color: black;
	color: black;
	cursor: pointer;
	height: 44px;
	line-height: 1.15;
	margin: 12px 0 0;
	position: relative;
	text-align: center;
	transform: translateZ(0);
	transition: all .2s,box-shadow .08s ease-in;
	width: 100%;
}

.sortbtn:hover {
box-shadow: rgba(50, 50, 93, .1);
}

</style>