<template>
  <!-- <GreetHello name="Lucho" heroName="Spiderman"/>
  <GreetHello :name="name" :heroName="channel"/> -->
  <!-- <ArticleComponent id="my-article"  :likes="50" :isPublished="true"/> -->
  <!-- <h3>AppComponent username {{ name }}</h3>
  <ComponentC /> -->
  <button @click="showPopUp = true">Show PopUp</button>
  <PopUp v-show="showPopUp" @close="closePopUp" />
</template>

<script>
// import GreetHello from './components/GreetHello.vue'
// import ArticleComponent from './components/ArticleComponent.vue'
// import ComponentC from './components/ComponentC.vue'
import PopUp from './components/PopUp.vue'

export default {
  name: 'App',
  components: {
    PopUp,
  },
  data() {
    return {
      showPopUp: false
    }
  },
  provide() {
      return {
      }
    },
  methods: { 
    closePopUp(name) {
      this.showPopUp = false
      console.log('name', name)
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
