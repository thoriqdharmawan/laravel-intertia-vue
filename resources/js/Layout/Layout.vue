<script setup>
</script>


<template>
  <div>
    <header>
      <nav>
        <div class="space-x-6">
          <Link :href="route('home')" class="nav-link">Home</Link>
        </div>
      </nav>
    </header>

    <main class="p-4">
      <slot></slot>
    </main>
  </div>
</template>