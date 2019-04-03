<template>
    <v-app>
        <article id="app" class="App">
            <Notes/>
        </article>
    </v-app>
</template>

<script>
    import Notes from './components/Notes/Notes.vue';
    import './App.scss';

    export default {
        name: 'app',
        components: {
            Notes
        },
    }
</script>
