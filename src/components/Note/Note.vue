<template>
    <section class="Note">
        <p class="Note__about">Note #{{number}} created on {{date.toLocaleString()}}</p>
        <p class="Note__text">{{text}}</p>
    </section>
</template>

<script>
    import './Note.scss';
    export default {
        name: "Note",
        props: ['text', 'date', 'number']
    }
</script>
