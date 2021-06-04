<template>
    <div>
        <nav class="navbar navbar-light bg-light fixed-top">
            <div class="container-fluid container-md">
                <a class="navbar-brand" href="#">
                    <img
                        src="@/assets/LexiconBig.png"
                        alt=""
                        height="30"
                        class="d-inline-block align-text-top"
                    />
                </a>
                <div v-if="!signedIn">Please Log In</div>
                <div v-else>
                    Logged in as {{ username }}
                    <button v-on:click="logOutUser" class="btn btn-danger">
                        Log out
                    </button>
                </div>
            </div>
        </nav>
    </div>
</template>

<script>
export default {
    props: {
        signedIn: {
            type: Boolean,
        },
        username: {
            type: String,
        },
    },
    methods: {
        logOutUser: function() {
            this.$emit("logOutUser");
        },
    },
};
</script>

<style scoped></style>
