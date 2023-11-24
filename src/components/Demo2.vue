<template>
    <h1>With reactive</h1>
    <h2>{{ firstName }} {{ lastName }}</h2>
    <hr />
</template>

<script>
import { reactive, toRefs } from 'vue'
export default {
    name: "Demo2",
    setup() {
        const state = reactive({
            firstName : "Shams",
            lastName : "ALSAADI"
        })
        setTimeout(()=>{
            state.firstName = "Mohamad",
            state.lastName = "ALJIBAOUI"
        }, 2000)
     return toRefs(state)
    }
}
</script>

<style></style>