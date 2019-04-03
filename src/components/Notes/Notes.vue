<template>
    <article>
        <NoteForm v-on:addnote="addNote"/>
        <p>I have {{notes.length}} notes:</p>
            <Note v-for="(note,index) in sortedNotes" v-bind:text=note.text v-bind:date="note.date" v-bind:number="notes.length-index"/>
    </article>
</template>

<script>
    import Note from '../Note/Note.vue';
    import NoteForm from '../NoteForm/NoteForm.vue';

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
        },
        computed:{
            sortedNotes:function () {
                return this.notes.sort((a,b)=>b.date - a.date);
            }
        }
    }
</script>
