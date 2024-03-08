<template>
    <p> {{ greeting }} {{ name }}</p>
    <p v-text="question"></p>
    <p v-html="htmlData" v-bind:id="id" v-bind:class="id" v-bind:style="style"> </p>
    <!-- v-html is for when you want to use html elements in your 'data()' -->
    <!-- v-bind:id will bind a dynamic id 'id' from 'data()' below to the element (p) -->
    <!-- v-bind:class will bind a dynamic class 'id' from 'data()' below to the element (p) -->
    <!-- v-bind:style will bind a dynamic style 'style' from 'data()' below to the element (p) -->
    <!-- With Vue3 you can remove 'v-bind' and just use :id="id" for example and it will still work -->
  
    <button v-on:click="name = 'Superman'"> Change Name </button>
    <!-- v-on:click used here will change the 'name' attribute from 'data()' when the button is clicked -->
    <!-- Can use '@click' instead of 'v-on:click' -->
  
    <!-- Counter App -->
    <h2>{{ count }}</h2>
    <button @click="increment(2)"> Add </button>
    <button @click="decrement(2)"> Sub </button>
    <!-- Calling the increment and decrement methods defined in the script below -->
  
    <!-- Condtional Rendering -->
    <h2 v-if="number === 0"> This is zero </h2>
    <h2 v-else-if="number < 0"> This is negative </h2>
    <h2 v-else-if="number > 0"> This is positive </h2>
    <h2 v-else> This is not a number </h2>
  
    <h2 v-show="isVisible"> Data is visible </h2>
    <!-- v-show means the element only shows if true (Example: if isVisible is true)-->
    <!-- element remains in the DOM, with style="display: none;" -->
    <h2 v-if="isVisible"> Data is visible </h2>
    <!-- v-if would be unmounted from the DOM, since isVisible = false -->
    <!-- unmounting and remounting is expensive, so use v-show if something is commonly used -->
  
    <div v-if="fruitsVisible">
      <h2> Apple </h2>
      <h2> Mango </h2>
      <h2> Banana </h2>
    </div> 
    <!-- using div is expensive because it appears in the DOM -->
    <!-- use template instead as it wont be visible in the DOM -->
    <template v-if="fruitsVisible">
      <h2> Apple </h2>
      <h2> Mango </h2>
      <h2> Banana </h2>
    </template>
  
  </template>
  
  <script>
  export default {
    name: 'App',
  
    data() { // data binding to <template> above
      return {
        name: 'Francis',
        greeting: 'Hello',
        question: 'How are you?',
        htmlData: '<b>I am HTML</b>',
        id: 'new',
  
        // Counter App
        count: 0,
        style: {
          color: 'red',
          backgroundColor: 'black' // notice use of camelCase here!
        },
  
        // Conditonal Rendering
        number: 0,
        isVisible: false,
        fruitsVisible: true
      }
    },
  
    methods: {
      increment(num) {
        this.count += num
      },
  
      decrement(num) {
        this.count -= num
      }
    }
  }
  </script>
  
  <style>
  #app {
    
  }
  </style>
  