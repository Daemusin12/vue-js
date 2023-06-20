<template>
  <div>
    <button @click="incrementCount">Clicked {{ count }} times</button>
  </div>
</template>

<script>
// import CounterMixin from '../mixins/counter'
import userCounter from '../composables/userCounter'

export default {
    name: 'ClickCounter',
    setup() {
      const { count, incrementCount } = userCounter(100, 10)

      return {
        count,
        incrementCount,
      }
    }
    // mixins: [CounterMixin],
}
</script>

<style>

</style>