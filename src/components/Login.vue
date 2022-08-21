<template>
    <img class="logo" src="../assets/restro-logo.png" />
    <h1>Login </h1>
    <div class="login">

        <input type="text" v-model="email" placeholder="Enter Email" />
        <input type="password" v-model="password" placeholder="Enter Password" />
        <button v-on:click="login">Login Up</button>
        <p>
            <router-link to="/sign-up">Sign-Up</router-link>
        </p>

    </div>


</template>

<script>
import axios from 'axios'
import { ReadableStreamDefaultReader } from 'node:stream/web';
export default {
    name: 'Login',
    data() {
        return {
            email: "",
            password: "",
        };
    },
    methods: {
        async login() {
            let result = await axios.get(
                'http://localhost:3000/user?email=${this.email}&password=${this.password}'
            );
            console.warn(result);

        },
    },
};


</script>