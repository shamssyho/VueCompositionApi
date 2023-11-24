<template>
    <h1> Replace methode with ref</h1>
    <h3> {{ count }} </h3>
    <button @click="increment"> Increment </button>
    <hr />
</template>

<script>
import { ref } from 'vue'

export default {
    name : "ReplaceMethodWithRef",
    setup() {
        const count = ref(0)
        function increment(){
            count.value++
        }
        return {
            count,
            increment
        }
    }
}
</script>

<style>

</style>