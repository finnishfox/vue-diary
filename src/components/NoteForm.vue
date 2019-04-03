<template>
    <form>
        <label>
            <textarea v-model="text"></textarea>
        </label>
        <button v-on:click.prevent="addNote" :disabled="text.replace(/\s+/g, '')===''">Add Note</button>
    </form>
</template>

<script>
    export default {
        name: 'NoteForm',
        data: () => ({
            text: ''
        }),
        model: {
            event: 'addnote',
        },
        methods:{
            addNote: function () {
                this.$emit('addnote', this.text);
            }
        }

    }
</script>
