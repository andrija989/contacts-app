<template>
  <div>
    <nav>
      <router-link to="/contacts/list">Contacts</router-link>
      <router-link to="/contacts/add-contact">Add contact</router-link>
    </nav>
    <router-view />
  </div>
</template>

<script>

export default {
  name: 'app'
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.test {
  /* font-size: 300px; */
  color: red;
}
</style>
