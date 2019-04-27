<template>
    <div>
        <h2>Zalogowany jako {{username}}</h2>
        <button @click="$emit('logout')">Wyloguj</button>
        <h2>Spotkania</h2>
        <button @click="addNewMeeting()">Dodaj nowe spotkanie</button>
        <ol>
            <li v-for="meeting in meetings">
                {{ meeting }}
            </li>
        </ol>
    </div>

</template>

<script>
    export default {
      props: ['username'],
        data() {
          return {
              meetings: ['MWO', 'TO', 'INNE']
          }
        },
        methods: {
            addNewMeeting(meeting) {
                this.meetings.push('nowe');
            }
        }
    }
</script>