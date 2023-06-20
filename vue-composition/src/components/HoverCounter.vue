<template>
    <div>
      <h2 @mouseover="incrementCount">Hovered {{ count }} times</h2>
    </div>
  </template>
  
  <script>
  // import CounterMixin from '../mixins/counter'
  import userCounter from '../composables/userCounter'
  
  export default {
      name: 'HoverCounter',
      setup() {
      const { count, incrementCount } = userCounter()

      return {
        count,
        incrementCount,
        }
      },
      // mixins: [CounterMixin],
  }
  </script>
  
  <style>
  
  </style>