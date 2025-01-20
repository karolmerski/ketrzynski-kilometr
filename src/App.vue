<template>
  <div id="app">
    <HelloWorld msg="Welcome to Your Vue.js App"/>
    <NewComponent />
    <LoginForm />
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue';
import NewComponent from './components/NewComponent.vue';
import LoginForm from './components/LoginForm.vue';

export default {
  name: 'App',
  components: {
    HelloWorld,
    NewComponent,
    LoginForm
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
</style>