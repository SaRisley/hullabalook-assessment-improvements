<script setup>
import InStock from './InStock.vue';
import FilterBrands from './FilterBrands.vue';
import SortBy from './SortBy.vue';
import ItemCounter from './ItemCounter.vue';
</script>

<template>
    <main>
        <ul class="toolbar">
            <li class="toolbartext">Filter by: </li>
            <li><InStock/></li>
            <li><FilterBrands/></li>
            <li><SortBy/></li>
            <li class="counter"><ItemCounter/></li>
        </ul>
    </main>
</template>

<style scoped>
.toolbar {
	overflow: visible;
	height: 50px;
	border-radius: 25px;
	align-items: center;
	align-content: center;
	margin-top: 5%;
	margin-bottom: 5%;
	margin-left: 5%;
	margin-right: 5%;
	border-width: 5px;
	border-color: #000000;
	border-style: solid;
}

.toolbar li{
	position: relative;
	display: inline-block;
	padding-right: 30px;
	color: black;
	text-align: center;
	font-family: Arial, Helvetica, sans-serif;
}

.toolbartext{
	position: relative;
	display: inline-block;
	color:black;
	text-align: center;
	font-family: Arial, Helvetica, sans-serif;
}

.toolbar .counter {
	display: block;
	float: right;
}
</style>
