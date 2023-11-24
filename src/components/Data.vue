<template>
    <h1>
        Replace data with ref
    </h1>
    <h3>
        Options - {{ o_firstName }}
    </h3>
    <h3>
        Composition - {{ c_firstName }}
    </h3>
    <h3>
       {{ greetHero }}
    </h3>
    <hr />

    <h1>
        Replace data with reactive
    </h1>
    <h3>
       {{ reactiveGreetHero }}
    </h3>
    <h3>
        
    </h3>

    <hr />
</template>

<script>
import { reactive, ref } from 'vue'
export default {
    name: "Data",
    setup() {
        const c_firstName = ref('Mohamad') //Initial value
        const c_lastName = ref('ALSAADI') //Initial value
        const c_heroName = ref('super') //Initial value
        c_firstName.value = "Diana"
        const greet = `Hello ${c_firstName.value}`
        const greetHero = `Hello ${c_firstName.value} ${c_lastName.value} ${c_heroName.value}`
        console.log('c_firstName', c_firstName)
        
        const state = reactive({
            firstName : "princess",
            lastName : 'Diana',
            heroName : 'Wonder Women'
        })
        const reactiveGreetHero = `Hello ${state.firstName} ${state.lastName} a.k.a ${state.heroName}`

        return {
            c_firstName: c_firstName,
            c_lastName,
            c_heroName,
            greetHero,
            greet,
            reactiveGreetHero,
        }
    },

    data() {
        return {
            o_firstName: 'Shams'
        }
    }

}
</script>

<style></style>