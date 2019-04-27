<template>
    <form @submit.prevent="">
        <div>
            <label>{{header}}</label>
            <input type="email" v-model="email">
            <button @click="enter()">{{buttonLabel}}</button>
        </div>
    </form>
</template>

<script>
    export default {
        //ustawione przez parenta
        props: ['buttonLabel', 'header'],
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