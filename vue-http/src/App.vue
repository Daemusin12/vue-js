<template>
  <!-- <CreatePost />
  <PostList /> -->
  <ParentComponent />
</template>

<script>
// import PostList from './components/PostList.vue'
// import CreatePost from './components/CreatePost.vue'
import ParentComponent from './components/ParentComponent.vue'

export default {
  name: 'App',
  components: {
    ParentComponent,
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
