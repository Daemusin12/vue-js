<template>
  <h2>{{ 2 + 3 + 5 }}</h2>
  <h2>Add Method - {{ add(2, 3, 5) }}</h2>
  <h2>Multiply Method - {{ multiply(baseValue) }}</h2>
</template>

<script>
export default {
  name: 'MethodApp',
  data() {
    return {
      baseMultiplier: 5,
      baseValue: 2
    }
  },
  methods: {
    add(a, b, c) {
      return a + b + c
    },
    multiply(num) {
      return num * this.baseMultiplier
    }
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