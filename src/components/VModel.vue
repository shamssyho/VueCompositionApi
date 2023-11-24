<template>
  <div>
    <h1>v-model and composition API </h1>
    <input type="text" placeholder="First Name" v-model="fName">
    <input type="text" placeholder="Last Name" v-model="lName">
<br />
    <input type="text" placeholder="Hero Name" v-model="heroName">
    <input type="text" placeholder="First Name" v-model="firstName">
    <input type="text" placeholder="Last Name" v-model="lastName">
    <hr />
  </div>
</template>

<script>
import { ref, reactive, toRefs } from "vue"
export default {
    name : "Vmodel",

    setup(){
        const heroName = ref("");
        const state = reactive({
            firstname : "", 
            lastName : "",
        })
        return {
            heroName,
            ...toRefs(state)
        }
    },
    data(){
        return {
            fName : "",
            lName : ""

        }

    }
}
</script>

<style>

</style>