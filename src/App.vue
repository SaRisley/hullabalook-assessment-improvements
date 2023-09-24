<script setup>
import ProductGridItem from './components/ProductGridItem.vue';
import ToolBar from './components/ToolBar.vue';
</script>

<template>
  <main>
    <header>
      <h1 class="fancytitle">Product Listing Page</h1>
      <h2 class="fancysubtitle">by Sarah Risley </h2>
    </header>
    <ToolBar/>
    <ProductGridItem/>
  </main>    
</template>

<style>
.app {
  max-width: 1024px;
  margin: 0 auto;
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  color: #606569;
}

.fancytitle {
	font-weight: normal;
	font-size: 4.5em;
	text-align: center;
	text-decoration: underline;
	text-decoration-color: black;
	cursor: pointer;
	width: 605px;
	margin-left: auto;
	margin-right: auto;

	background-color: #CA4246;
	
    background-image: linear-gradient(
        45deg,
        #c500ab 16.666%, 
        #9500ff 16.666%, 
        #4166e1 33.333%, 
        #77ff00 33.333%, 
        #77ff00 50%, 
        #ffb300 50%, 
        #ffb300 66.666%, 
        #E16541 66.666%, 
        #ff0008 83.333%, 
        #ff0008 83.333%);
	
	background-size: 100%;
	background-repeat: repeat;
  
	-webkit-background-clip: text;
	-webkit-text-fill-color: transparent; 

	animation: rainbow-text-simple-animation-rev 0.75s ease forwards;
  }
  
  .fancytitle:hover{
	animation: rainbow-text-simple-animation 0.5s ease-out forwards;
}

.fancysubtitle {
	font-weight: normal;
	font-size: 3em;
	text-align: center;
	text-decoration-color: black;
	cursor: pointer;
	width: 605px;
	margin-left: auto;
	margin-right: auto;

	background-color: #CA4246;
	
    background-image: linear-gradient(
        45deg,
        #c500ab 16.666%, 
        #9500ff 16.666%, 
        #4166e1 33.333%, 
        #77ff00 33.333%, 
        #77ff00 50%, 
        #ffb300 50%, 
        #ffb300 66.666%, 
        #E16541 66.666%, 
        #ff0008 83.333%, 
        #ff0008 83.333%);
	
	background-size: 100%;
	background-repeat: repeat;
  
	-webkit-background-clip: text;
	-webkit-text-fill-color: transparent; 

	animation: rainbow-text-simple-animation-rev 0.75s ease forwards;
  }
  
  .fancysubtitle:hover{
	animation: rainbow-text-simple-animation 0.5s ease-out forwards;
}

@keyframes rainbow-text-simple-animation-rev {
  0% {
    background-size: 650%;
  }
  40% {
    background-size: 650%;
  }
  100% {
    background-size: 100%;
  }
}

  @keyframes rainbow-text-simple-animation {
  0% {
    background-size: 100%;
  }
  80% {
    background-size: 650%;
  }
  100% {
    background-size: 650%;
  }
}

</style>
