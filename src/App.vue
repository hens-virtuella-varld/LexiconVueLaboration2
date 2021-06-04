<template>
    <div id="app">
        <navbar
            v-on:logOutUser="logOutUser"
            v-bind:signedIn="signedIn"
            v-bind:username="user.username"
        ></navbar>
        <app-form
            v-bind:signedIn="signedIn"
            v-on:signInUser="signInUser"
        ></app-form>
    </div>
</template>

<script>
import Navbar from "./components/Navbar.vue";
import Form from "./components/Form.vue";
export default {
    components: {
        navbar: Navbar,
        "app-form": Form,
    },
    data() {
        return {
            signedIn: false,
            user: {
                username: "",
                password: "",
            },
        };
    },
    methods: {
        logOutUser: function() {
            this.signedIn = false;
            this.user.username = "";
            this.user.password = "";
        },
        signInUser: function(user) {
            this.user = user;
            this.signedIn = true;
        },
    },
};
</script>

<style></style>
