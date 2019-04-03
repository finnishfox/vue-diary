<template>
    <section>
        <p>{{text}}</p>
        <time>{{date.toLocaleString()}}</time>
    </section>
</template>

<script>
    export default {
        name: "Note",
        props: ['text','date']
    }
</script>
