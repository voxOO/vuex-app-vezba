<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <h1>{{ counter }}</h1>
    <button @click="increment">Increment</button>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import { mapGetters, mapActions } from 'vuex';

export default {
  name: 'app',
  components: {
    HelloWorld
  },
  computed: {
    ...mapGetters({
      counter: 'ModuleA/getCountText'
    }),
    // counter() {
    //   //return this.$store.state.counter;
    //   console.log({
    //     a: this.$store
    //   })
    //   return this.$store.getters.getCountText
    // }
  },
  methods : {
    ...mapActions ({
      increment: 'ModuleA/incrementAfterTwoSeconds'
    }),
    // increment() {
    //   //this.$store.commit('increment');
    //   this.$store.dispatch('incrementAfterTwoSeconds');
    // },
  }
}
</script>


<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
