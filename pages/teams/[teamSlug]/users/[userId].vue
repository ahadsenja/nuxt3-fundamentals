<script setup lang="ts">
const route = useRoute();
const message = computed(
  () =>
    `Hi i'm on team ${route.params.teamSlug}  and my user id is ${route.params.userId}`
);
</script>
<template>
  <div>
    <h1>{{ message }}</h1>
  </div>
</template>
