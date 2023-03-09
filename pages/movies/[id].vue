<script setup>
const route = useRoute();

// call useFectch for $fetch + useAsyncData shorthand
const { data } = await useFetch(
  `https://www.omdbapi.com/?apikey=f32d19b1&i=${route.params.id}`,
  {
    pick: ["Plot", "Title", "Poster"],
    key: `/movies/${route.params.id}`,
    // Error handling
    onResponse({ request, response }) {
      if (response._data.Error === "Incorrect IMDb ID.") {
        showError({ statusCode: 404, statusMessage: "Page Not Found." });
      }
    },
  }
);

useHead({
  title: data.value.Title,
  meta: [
    { name: "description", content: data.value.Plot },
    { property: "og:description", content: data.value.Plot },
    { property: "og:image", content: data.value.Poster },
    { name: "twitter:card", content: `summary_large_image` },
  ],
});

// full version
// const { data } = await useAsyncData(
//   `/movies/${route.params.id}`,
//   () => {
//     return $fetch(
//       `http://www.omdbapi.com/?apikey=f32d19b1&i=${route.params.id}`
//     );
//   },
//   {
//     pick: ["Plot", "Title"],
//   }
// );
</script>

<template>
  <div>
    <pre>
      {{ data }}
    </pre>
  </div>
</template>

<style scoped></style>
