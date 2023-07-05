<template>
    <li>
        <base-card>
            <header>
                <h3> {{ title }}</h3>
                <base-button @click="deleteRes(id)">Delete</base-button>
            </header>
            
            <p>{{ des }}</p>
            <nav>
                <a :href="link">Link</a>
            </nav>
        </base-card>
    </li>

</template>


<script>

    export default {
        props: ['id','title', 'des', 'link'],
        inject: ["deleteRes"],
        data(){
            return {

            };
        },
    }

</script>


<style scoped>
    * {
        font-weight: 800;
    }

    li  {
        margin: auto;
        max-width: 40rem;
    }

    header {
        display: flex;
        justify-content: space-between;
        align-items: center;
    }

    p {
        margin: 0.5rem 0;
    }

    h3 {
        font-size: 1.5rem;
        margin: 0.5rem 0;
    }

    a {
        color: orange;
    }

    a:hover, a:active {
        color: white;
        background-color: orange;
    }
</style>