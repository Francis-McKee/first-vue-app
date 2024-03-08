<template>
  <CountVue :count="count"/>
  <br/>
  <ButtonVue name="Add" @changeCount="count += 1"/>
  <ButtonVue name="Sub" @changeCount="count -= 1"/>
</template>

<script>
import CountVue from './components/Count.vue'
import ButtonVue from './components/Button.vue'

export default {
  name: 'App',

  components: {
    CountVue,
    ButtonVue
  },

  data() {
    return {
      count: 0
    }
  }

}
</script>

<style>
#app {
  
}
</style>
