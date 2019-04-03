<template>
    <form class="NoteForm">
        <label>
            <v-text-field v-model="text" label="Hello, Diary! It's me..." solo></v-text-field>
        </label>
        <v-btn
                v-on:click.prevent="addNote"
                :disabled="text.replace(/\s+/g, '')===''"
                color="primary"
                class="NoteForm__button">Add Note
        </v-btn>
    </form>
</template>

<script>
    import './NoteForm.scss';
    export default {
        name: 'NoteForm',
        data: () => ({
            text: ''
        }),
        model: {
            event: 'addnote',
        },
        methods: {
            addNote: function () {
                this.$emit('addnote', this.text);
                this.text = '';
            }
        }

    }
</script>
