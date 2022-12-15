<script setup lang="ts">
import { RouterLink, RouterView } from 'vue-router'
import { useAuthStore } from '@/stores/auth'

const store = useAuthStore();

function logout() {
  store.logout();
}
</script>

<template>
  <div class="min-h-screen bg-gray-100">
    <header class="p-8">
      <nav class="flex flex-row list-none">
        🍃🥾
        <RouterLink to="/" class="ml-4">Dashboard</RouterLink>
        <RouterLink to="/products" class="ml-4">Products</RouterLink>
        <a href="#" class="ml-4 text-indigo-400" @click="logout">Logout</a>
      </nav>
    </header>
    <main class="p-8 w-1/2">
      <RouterView />
    </main>
  </div>
</template>
