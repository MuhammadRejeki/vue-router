<template>
<nav>
    <router-link to="/">Home</router-link> |
    <router-link :to="{ name:'aboutnya' }">About</router-link> |
    <router-link :to="{ name:'jobs' }">Jobs</router-link>
</nav>
<div class="contain">
    <router-view />
</div>
<div class="actions">
  <button @click="redirect">Redirect</button>
  <button @click="back">Back</button>
  <button @click="forward">Forward</button>
</div>
</template>

<script>

export default {
  data(){
    return {};
  },
  methods:{
    redirect(){
      this.$router.push({name:'home'})
    },
    back(){
      this.$router.go(-1)
    },
    forward(){
      this.$router.go(1)
    }
  }
}
</script>


<style>
#app {
    padding: 20px;
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
}

nav a {
    font-weight: bold;
    color: #2c3e50;
    text-decoration: none;
    padding: 10px;
    border-radius: 4px;
}

nav a.router-link-exact-active {
    color: white;
    background: crimson;
}

.contain {
    width: 70%;
    background-color: #f5f5f5;
    border: 1px solid #e3e3e3;
    border-radius: 4px;
    margin: 30px auto;
    padding: 10px;
    box-shadow: inset 0 1px 1px rgba(0,0,0,.05);
    min-height: 500px;
}

.contain p {
    color: #333;
    font-family: 'Times New Roman', Times, serif;
    text-align: justify;
}

button {
  margin: 0 10px;
  padding: 10px;
  border: none;
  border-radius: 4px;
}
</style>
