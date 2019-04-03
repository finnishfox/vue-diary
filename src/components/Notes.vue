<template>
    <article>
        <NoteForm v-on:addnote="addNote"/>
        <p>I have {{notes.length}} notes</p>
        <section v-for="note in notes">
            <Note v-bind:text=note.text v-bind:date="note.date"/>
        </section>
    </article>
</template>

<script>
    import Note from './Note.vue';
    import NoteForm from './NoteForm.vue';

    export default {
        name: "Notes",
        data: () => ({
            notes: [
                {text: '1st note', date: new Date()},
                {text: '2nd note', date: new Date()},
            ]
        }),
        components: {
            Note,
            NoteForm
        },
        methods: {
            addNote: function (text) {
                const newNote = {text: text, date: new Date()};
                this.notes.push(newNote);
            }
        }
    }
</script>
