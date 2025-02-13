<script setup>
import { usePage } from '@inertiajs/vue3';
import { computed } from 'vue';

const page = usePage()

const user = computed(() => page.props.auth.user)
</script>

<template>

  <Head :title="` | ${$page.component}`"></Head>
  <h2>{{ user }}</h2>

  <Link class="mt-[1400px] block" href="/" preserve-scroll>Refresh</Link>
</template>