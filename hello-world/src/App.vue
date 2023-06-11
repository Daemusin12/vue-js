<template>
  <div>{{ greet }} {{ name }}</div>
  <div v-text="channel"></div>
  <div v-html="hack"></div>
  <h2 v-bind:id="headingId">Heading</h2>
  <button v-bind:disabled="isDisabled">Bind</button>
</template>

<script>
export default {
  name: 'App',
  data() {
    return {
      greet: "Hello",
      name: "Engr. Leonel J. Felezario",
      channel: "Hotdog",
      hack: `<a href="#" onclick="alert('All your base are belong to us!')">CLICK ME!<a/>`,
      headingId: 'heading',
      isDisabled: true
    };
  },
};
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
