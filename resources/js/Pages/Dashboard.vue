<script setup>
import { usePage } from '@inertiajs/vue3';
import { computed } from 'vue';

const page = usePage()

const user = computed(() => page.props.auth.user)
</script>

<template>

  <Head :title="` | ${$page.component}`"></Head>
  <div>
    <p v-if="page.props.flash.greet" class="p-4 bg-green-200">{{ page.props.flash.greet }}</p>
    <h1 class="title">Welcome back {{ user.name }}</h1>
  </div>
</template>