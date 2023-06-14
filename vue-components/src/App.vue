<template>
  <GreetHello name="Lucho" heroName="Spiderman"/>
  <GreetHello :name="name" :heroName="channel"/>
</template>

<script>
import GreetHello from './components/GreetHello.vue'

export default {
  name: 'App',
  components: {
    GreetHello,
  },
  data() {
    return {
      name: 'Leozzio',
      channel: 'Hotdog'
    }
  }

}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
