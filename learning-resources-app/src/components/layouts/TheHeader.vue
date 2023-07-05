<template>
    <header>
        <h1>{{title}}</h1>
    </header>
</template>


<script>

    export default {
        props: ['title']
    }
</script>


<style scoped>
    header {
        width: 100%;
        height: 7rem;
        display: flex;
        justify-content: center;
        align-items: center;
        background-color: orange;
    }

    header h1 {
        color: white;
        font-size: 3.5rem;
        font-weight: 700;
        margin: 0;
    }
</style>