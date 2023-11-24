<template>
    <h1>
        Relace Watchers with ref
    </h1>
    <input type="text" placeholder="First name" v-model="firstName">
    <input type="text" placeholder="Last name" v-model="lastName">
    <hr />
    <h1>
        Relace Watchers with reactive
    </h1>
    <input type="text" placeholder="First name" v-model="fName">
    <input type="text" placeholder="Last name" v-model="lName">
    <hr />
</template>

<script>
import { ref, watch, reactive, toRefs } from 'vue'
export default {
    name: "ReplacingWatchers",
    setup() {

        const state = reactive({
            fName: "",
            lName: ""
        })
        watch(state, function(newValue, oldValue){
            console.log("fName old value", oldValue.fName)
            console.log("fName new value", newValue.fName)
            console.log("fName old value", oldValue.lName)
            console.log("fName new value", newValue.lName)
        })

        const firstName = ref('')
        const lastName = ref('shams')

        watch([firstName, lastName], (newValues, oldValues) => {
            console.log("firstName old value", oldValues[0])
            console.log("firstName new value", newValues[0])
            console.log("lastName old value", oldValues[1])
            console.log("lastName new value", newValues[1])
        }, {
            immediate: true,
        })
        return {
            firstName,
            lastName,
            ...toRefs(state)
        }
    }
}
</script>

<style></style>