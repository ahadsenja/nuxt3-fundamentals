<template>
  <div>
    <nav>
      <ul>
        <li>
          <NuxtLink class="nuxt-link" to="/">Home</NuxtLink>
        </li>
        <li>
          <NuxtLink class="nuxt-link" to="/movies">Movies</NuxtLink>
        </li>
        <li>
          <NuxtLink
            class="nuxt-link"
            to="https://nuxt.com/docs/getting-started/routing"
            >Nuxt Routing</NuxtLink
          >
        </li>
      </ul>
    </nav>
    <NuxtPage />
  </div>
</template>

<style scoped>
nav {
  background-color: cadetblue;
  padding: 10px;
  margin: 0px;
}

nav ul {
  display: flex;
  gap: 30px;
  list-style-type: none;
}

nav ul li .nuxt-link {
  color: white;
  text-decoration: none;
}
</style>
