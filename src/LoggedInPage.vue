<template>
    <div>
        <h2>Zalogowany jako {{username}}</h2>
        <button @click="$emit('logout')">Wyloguj</button>
    </div>
</template>

<script>
    export default {
      props: ['username']
    }
</script>