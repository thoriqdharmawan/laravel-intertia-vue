<script setup>
defineProps({
  user: String
})
</script>

<template>

  <Head title=" | About"></Head>
  <div>
    <h1>About page {{ user }}</h1>
  </div>
</template>
