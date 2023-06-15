<template>
  <div>
    <h2>
        This is a PopUp
    </h2>
    <button @click="$emit('close', 'Leozzio')">Close PopUp</button>
  </div>
</template>

<script>
export default {
    name: 'PopUp',
    emits: ['close']
}
</script>

<style>

</style>