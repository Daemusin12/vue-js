<template>
  <div>Hello {{ fullName }}</div>
</template>

<script>
import { computed } from 'vue'
export default {
    name: 'PersonGreeting',
    setup(props) {
        const fullName = computed(() => {
            return `${props.firstName} ${props.lastName}`
        })
        return {
            fullName,
        }
    },
    props: ['firstName', 'lastName'],
    // computed: {
    //     fullName() {
    //         return `${this.firstName} ${this.lastName}`
    //     }
    // }
}
</script>

<style>

</style>