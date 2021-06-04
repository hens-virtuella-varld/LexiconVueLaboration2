<template>
    <div class="d-flex justify-content-center align-items-center vh-100">
        <form v-on:submit.prevent="signInUser" class="w-50 shadow p-5">
            <div class="mb-3">
                <label for="exampleInputEmail1" class="form-label">Name</label>
                <input
                    type="text"
                    v-model="user.username"
                    class="form-control"
                    id="exampleInputEmail1"
                    aria-describedby="emailHelp"
                />
            </div>
            <div class="mb-3">
                <label for="exampleInputPassword1" class="form-label"
                    >Password</label
                >
                <input
                    type="password"
                    v-model="user.password"
                    class="form-control"
                    id="exampleInputPassword1"
                />
            </div>
            <button
                v-bind:disabled="signedIn"
                type="submit"
                class="btn btn-danger"
            >
                Submit
            </button>
        </form>
    </div>
</template>

<script>
export default {
    props: {
        signedIn: {
            type: Boolean,
        },
    },
    data() {
        return {
            user: {},
        };
    },
    methods: {
        signInUser: function() {
            this.$emit("signInUser", this.user);
            this.user = {};
        },
    },
};
</script>

<style></style>
