<template>
    <form @submit.prevent="">
        <div>
            <label>Zaloguj się e-mailem</label>
            <input type="email" v-model="email">
            <button @click="enter()">Wchodzę</button>
        </div>
    </form>
</template>

<script>
    export default {
        data() {
            return {
                email: ''
            }
        },
        methods: {
            enter() {
                this.$emit('login', this.email);
            }
        }
    }
</script>