<script setup>
const route = useRoute();

const { data } = await useAsyncData(
  `/movies/${route.params.id}`,
  () => {
    return $fetch(
      `http://www.omdbapi.com/?apikey=f32d19b1&i=${route.params.id}`
    );
  },
  {
    pick: ["Plot", "Title"],
  }
);
</script>

<template>
  <div>
    <pre>
      {{ data }}
    </pre>
  </div>
</template>

<style scoped></style>
