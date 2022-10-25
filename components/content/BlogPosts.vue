<script setup>
const { data } = await useAsyncData(() => {
  return queryContent('/posts/').find()
})
</script>

<template>
<div>
  <div v-for="post in data" :key="post._id">
    <h2>{{ post.title }}</h2>
    <p><small>{{ post.createdAt }}</small></p>
    <p>{{ post.description }}</p>
    <NuxtLink :to="post._path">
      Read more...
    </NuxtLink>
  </div>
</div>
</template>

<style scoped>

</style>