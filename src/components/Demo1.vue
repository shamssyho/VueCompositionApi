<template>
    <h1>With ref</h1>
    <h2>{{ name }}</h2>
    <hr />
</template>

<script>
import { ref } from 'vue'
export default {
    name: "Demo1",
    setup() {
        const name = ref("Mohamad")
        setTimeout(() => {
            name.value = "Codevolution"
        }, 2000)
        return {
            name,
        }
    }


}
</script>

<style></style>