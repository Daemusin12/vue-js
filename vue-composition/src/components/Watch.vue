<template>
  <div>
    <input type="text" placeholder="Name" v-model="name" />

    <input type="text" placeholder="First Name" v-model="firstName" />
    <input type="text" placeholder="Last Name" v-model="lastName" />

    <input type="text" placeholder="Reactive First Name" v-model="fName" />
    <input type="text" placeholder="Reactive Last Name" v-model="lName" />
    <input type="text" placeholder="Reactive Hero Name" v-model="options.heroName" />
  </div>
</template>

<script>
import { ref, watch, reactive, toRefs } from 'vue'
import _ from 'lodash'
export default {
    name: 'WatchComponent',
    setup() {

        const state = reactive({
        fName: '',
        lName: '',
        options: {
            heroName: ''
        }
        })

        // watch(() => {
        //     return { ...state }
        // }, function(newValue, oldValue) {
        //     console.log('fName Old value', oldValue.fName)
        //     console.log('fName New value', newValue.fName)
        //     console.log('lName Old value', oldValue.lName)
        //     console.log('lName New value', newValue.lName)
        // })

        watch(() => _.cloneDeep(state.options), function(newValue, oldValue) {
            console.log('fname Old value', oldValue)
            console.log('fname New value', newValue)
        }, {deep: true,})

        const firstName = ref('')
        const lastName = ref('Wayne')

        watch([firstName, lastName], (newValues, oldValues) => {
            console.log('firstName Old value', oldValues[0])
            console.log('firstName New value', newValues[0])
            console.log('lastName Old value', oldValues[1])
            console.log('lastName new value', newValues[1])
        }, {
            immediate: true,
        })

        return {
            firstName,
            lastName,
            ...toRefs(state)
        }
    },
    data() {
        return {
            name: '',
        }
    },
    watch: {
        name(newValue, oldValue) {
            console.log('Old value', oldValue)
            console.log('Name value', newValue)
        }
    }
}
</script>

<style>

</style>