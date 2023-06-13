<template>
  <h2>{{ name }}</h2>
  <div>
    <button v-on:click="changeName($event), increment(1, $event)">Change name</button>
  </div>
  <h2>{{ count }}</h2>
  <div>
    <button @click=increment(2)>Increment 2 </button>
    <button @click=decrement(3)>Decrement 3</button>
  </div>
</template>

<script>
export default {
  name: 'EventHandlingApp',
  data() {
    return {
      name: 'Engr. Leonel J. Felezario',
      count: 0,
    }
  },
  methods: {
    changeName(event) {
      this.name = 'Superman',
      console.log('Event', event)
    },
    increment(num, event) {
      this.count += num,
      console.log('Event', event)
    },
    decrement(num) {
      this.count -= num
    },
  },
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