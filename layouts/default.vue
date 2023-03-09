<script setup>
const user = useUser();
</script>

<template>
  <nav>
    <NuxtLink class="nuxt-link" to="/">Home</NuxtLink>

    <NuxtLink class="nuxt-link" to="/movies">Movies</NuxtLink>

    <NuxtLink class="nuxt-link" to="/login" v-if="!user.isLoggedIn"
      >Login</NuxtLink
    >

    <a
      class="nuxt-link"
      href="#"
      v-else
      @click.prevent="user.isLoggedIn = false"
      >Logout</a
    >
  </nav>

  <slot></slot>
</template>

<style scoped>
nav {
  background-color: cadetblue;
  padding: 10px;
  margin: 0px;
  display: flex;
  gap: 10px;
}

nav .nuxt-link {
  color: white;
  text-decoration: none;
}

nav .nuxt-link:hover {
  color: antiquewhite;
}
</style>
