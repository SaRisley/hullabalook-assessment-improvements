<script setup>
// import { ref,onMounted, onBeforeMount } from 'vue';

const scrollToTop = () => {
        window.scrollTo({ top: 0, left: 0, behavior: 'smooth' });
    }

</script>

<template>
    <div>
        <button class="scrollbutton" @click="scrollToTop"><i class="arrow up"></i></button>
    </div>
</template>

<style>
.arrow {
    border: solid black;
    border-width: 0 3px 3px 0;
    display: inline-block;
    padding: 3px;
}

.up {
    transform: rotate(-135deg);
    -webkit-transform: rotate(-135deg);
}

.scrollbutton {
    position: fixed; /* Fixed/sticky position */
    bottom: 20px; /* Place the button at the bottom of the page */
    right: 20px; /* Place the button 30px from the right */
    z-index: 99; /* Make sure it does not overlap */
    border: none; /* Remove borders */
    outline: none; /* Remove outline */
    background-color: whitesmoke;
    color: rgb(0, 0, 0); /* Text color */
    cursor: pointer; /* Add a mouse pointer on hover */
    padding: 15px; /* Some padding */
    border-radius: 10px; /* Rounded corners */
    border-style: solid;
    border-color: black;
    font-size: 18px; /* Increase font size */
}

.scrollbutton:hover {
  background-color: #555; /* Add a dark-grey background on hover */
}
</style>