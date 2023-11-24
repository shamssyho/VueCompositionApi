<template>
    <h1>Replacing computed props</h1>
    <h3>Full name is (normal methode): {{ fullName }}</h3>
    <input type="text" placeholder="First Name" v-model="fName">
    <input type="text" placeholder="Last Name" v-model="lName">
    <div>
        <h3>The full name with ref and computed is : {{ fullNameShow }}</h3>
        <input type="text" placeholder="First Name" v-model="firstName">
        <input type="text" placeholder="Last Name" v-model="lastName">
    </div>
    <div>
        <h3>The additional information with reactive and computed is : {{ additionalInfo }}</h3>
        <input type="text" placeholder="Work" v-model="work">
        <input type="text" placeholder="Studies" v-model="study">
    </div>
    <hr />
</template>

<script>
import { ref, computed, reactive, toRefs } from 'vue'
export default {
    name: "ReplacingComputedProps",
    setup() {
        const firstName = ref("")
        const lastName = ref("")

        const fullNameShow = computed(function (){
            return `${firstName.value} ${lastName.value}`
        })

        const state = reactive({
            work : '',
            study : ''
        })
        const additionalInfo = computed(function() {
            return ` ${state.work},  ${state.study}`
        })

        return {
            firstName,
            lastName,
            fullNameShow,
            ...toRefs(state),
            additionalInfo
        }
    },
    data() {
        return {
            fName: "",
            lName: "",
        }
    },
    computed: {
        fullName() {
            return `${this.fName} ${this.lName}`
        }
    }

}
</script>

<style></style>