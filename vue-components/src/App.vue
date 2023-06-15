<template>
  <!-- <GreetHello name="Lucho" heroName="Spiderman"/>
  <GreetHello :name="name" :heroName="channel"/> -->
  <!-- <ArticleComponent id="my-article"  :likes="50" :isPublished="true"/> -->
  <!-- <h3>AppComponent username {{ name }}</h3>
  <ComponentC /> -->
  <!-- <button @click="showPopUp = true">Show PopUp</button>
  <PopUp v-show="showPopUp" @close="closePopUp" /> -->
  <!-- <InputComponent v-model="name" /> -->
    <!-- <CardComponent></CardComponent>
    <CardComponent>Card content</CardComponent>
    <CardComponent> 
        <h2>Card content</h2>
    </CardComponent>
    <CardComponent>
      <img src="https://picsum.photos/200"/>
    </CardComponent>
    <CardComponent>
      <template v-slot:header>
        <h3>Header</h3>
      </template>
      <template v-slot:default>
        <img src="https://picsum.photos/200">
      </template>
      <template v-slot:footer>
        <button>View Details</button>
      </template>
    </CardComponent> -->
    <NameList >
      <template v-slot:default="slotProps">
         {{ slotProps.firstName }} {{ slotProps.lastName }}
      </template>
    </NameList>
    <NameList>
      <template v-slot:default="slotProps">
         {{ slotProps.lastName }} {{ slotProps.firstName }}
      </template>
    </NameList>
    <NameList>
      <template v-slot:default="slotProps">
         {{ slotProps.firstName }}
      </template>
    </NameList>
</template>

<script>
// import GreetHello from './components/GreetHello.vue'
// import ArticleComponent from './components/ArticleComponent.vue'
// import ComponentC from './components/ComponentC.vue'
// import PopUp from './components/PopUp.vue'
// import InputComponent from './components/InputComponent.vue';
// import CardComponent from './components/CardComponent.vue';
import NameList from './components/NameList.vue';

export default {
  name: 'App',
  components: {
    NameList,
  },
  data() {
    return {
    }
  },
  provide() {
      return {
      }
    },
  methods: { 
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
