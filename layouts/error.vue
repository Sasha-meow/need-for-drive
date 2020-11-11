<template>
  <div>
    <h1 v-if="error.statusCode === 404">Ooops...page not found!</h1>
    <h1 v-else>An error occurred</h1>
    <NuxtLink to="/">Back to previous page</NuxtLink>
  </div>
</template>

<script>
  export default {
    props: ['error'],
    layout: 'error' // you can set a custom layout for the error page
  }
</script>
<style>
  h1{
    color: rgba(14, 194, 97, 1);
    font-style: normal;
    font-weight: bold;
  }
</style>
