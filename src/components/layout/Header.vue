<template>
  <div id="nav" class="header">
    <h1>
      <router-link to="/">Todo App</router-link>
    </h1>
    <router-link to="/about">About</router-link>
    <router-link to="/contact">Contact</router-link>
  </div>
</template>

<script>
export default {
  name: "Header"
};
</script>

<style scoped>
.header {
  background-color: #000;
  color: #fff;
  text-align: center;
  padding: 10px;
}

.header a {
  color: #fff;
  padding-right: 5px;
  text-decoration: none;
  margin: 0 10px 0 0;
}

h1 {
  margin-right: auto;
  margin-left: 10px;
}

#nav {
  display: flex;
  width: 100%;
  justify-content: flex-end;
  align-items: center;
}
</style>
