<template>
    <div class="page-my-account">
        <div class="columns is-multiline">
            <div class="column is-12">
                <h1 class="title"> My account</h1>
            </div>

            <div class="column is-12">
                <button class="button is-danger" @click="logout()"> Log out </button>
            </div>

            <hr>

            <div class="column is-12">
                <h2 class="subtitle">My orders</h2>

                <!-- <OrderSummary
                    v-for="order in orders"
                    v-bind:key="order.id"
                    v-bind:order="order" /> -->
            </div>
            
        </div>
    </div>
</template>

<script>
import axios from 'axios'




export default {
    name: "MyAccount",
    
    methods: {
        logout() {
            axios.defaults.headers.common["Authorization"] = ""

            localStorage.removeItem("username")
            localStorage.removeItem("userid")
            
            this.$store.commit('removeToken')

            this.$router.push('/')
        },
    },

}
</script>