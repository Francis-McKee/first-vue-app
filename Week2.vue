<template>

    <!-- Passing Props -->
    <GreetVue name="Sam"/>
    <GreetVue name="Mike"/>
    <GreetVue :name="name"/>
  
    <!-- Emitter Example -->
    <button @click="isPopupVisible = true"> Show Popup </button>
    <PopupVue v-if="isPopupVisible" @close="isPopupVisible = false"/>
  
    <!-- Slots Example -->
    <CardVue> This is our first slot </CardVue>
    <CardVue> <h1> This is our first slot </h1> </CardVue>
    <CardVue> <img src="https://placehold.co/300x200"/> </CardVue>
    <CardVue>
      <template v-slot:header>
        <h2> This is card heading </h2>
      </template>
      <template v-slot:default>
        <img src="https://placehold.co/300x200"/>
      </template>
      <template v-slot:footer>
        <b> This is card heading </b>
      </template>
    </CardVue>
</template>
  
<script>
  import GreetVue from './components/Greet.vue'
  import PopupVue from './components/Popup.vue'
  import CardVue from './components/Card.vue'
  
  export default {
    name: 'App',
  
    components: {
      GreetVue,
      PopupVue,
      CardVue
    },
  
    data() {
      return {
        name: 'Superman',
        isPopupVisible: false
      }
    }
  
  }
</script>
  
<style>
  #app {
    
  }
</style>
  