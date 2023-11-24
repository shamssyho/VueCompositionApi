<template>
    <h1> Replace methode with reactive</h1>
    <h3>{{ first }} {{ last }}</h3>
    <button @click="changeHero"> Cahnge </button>
    <hr />
</template>

<script>
import { reactive, toRefs } from 'vue'
export default {
    name :"ReplaceMethodWithReactive",
    setup(){
        const state = reactive({
            first : "Moho",
            last : "ALSAADI"
        }) 

        function changeHero(){
            state.first = "Shams",
            state.last = "ALSL"
        }

        return {
            ...toRefs(state), // pour ne pas utuliser state.first et state.last
            changeHero
        }


    }
}
</script>

<style></style>