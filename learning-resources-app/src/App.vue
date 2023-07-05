<template> 
  <the-header title="Remember Me"></the-header>
  <the-resources></the-resources>
</template>




<script>
import TheHeader from './components/layouts/TheHeader.vue';
import TheResources from './components/learning-resources/TheResources.vue';
export default {
    components: {
      TheHeader,
      TheResources
    },
    data() {
      return {



      };

    }
  
  }

</script>


<style>
  * {
    box-sizing: border-box;
  }

  body {
    margin: 0;
  }

</style>









































<!-- <template>
  <img alt="Vue logo" src="./assets/logo.png">
  <HelloWorld msg="Dit me cuoc doi"/>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  components: {
    HelloWorld
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style> -->
