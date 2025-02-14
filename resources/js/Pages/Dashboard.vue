<script setup>
import { usePage } from '@inertiajs/vue3';
import { computed } from 'vue';

const page = usePage()

const user = computed(() => page.props.auth.user)
</script>

<template>

  <Head :title="` | ${$page.component}`"></Head>
  <div>
    <h1 class="title">Welcome back {{ user.name }}</h1>
  </div>
</template>