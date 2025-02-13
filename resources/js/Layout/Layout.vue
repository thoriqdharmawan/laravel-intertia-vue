<script setup>
import { usePage } from '@inertiajs/vue3';
import { computed } from 'vue';

const page = usePage()

const user = computed(() => page.props.auth.user)
</script>


<template>
  <div>
    <header class="bg-indigo-600 text-white">
      <nav class="flex items-center justify-between p-4 max-w-screen-lg mx-auto">
        <h2>{{ user }}</h2>
        <div class="space-x-6">
          <Link :href="route('home')">Home</Link>
          <Link :href="route('about')">About</Link>
        </div>
      </nav>
    </header>

    <main class="p-4">
      <slot></slot>
    </main>
  </div>
</template>