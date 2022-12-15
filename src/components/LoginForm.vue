<script lang="ts" setup>
import { reactive, ref } from 'vue';
import { useAuthStore } from '@/stores/auth';

const user = reactive({
  username: '',
  password: '',
});

function onSubmit() {
  console.log(user);
  if (user.username != '' && user.password != '') {
    useAuthStore().login(user.username, user.password);
  }
}
</script>

<template>
  <form class="bg-white p-8 rounded-md shadow-md" @submit.prevent="onSubmit">
    <div class="mb-4">
      <label for="username" class="block text-gray-700 text-sm font-bold mb-2">Username</label>
      <input type="text" id="username" placeholder="Username" v-model="user.username"
        class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline">
    </div>
    <div class="mb-6">
      <label for="password" class="block text-gray-700 text-sm font-bold mb-2">Password</label>
      <input type="password" id="password" placeholder="Password" v-model="user.password"
        class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 mb-3 leading-tight focus:outline-none focus:shadow-outline">
    </div>
    <div class="flex items">
      <button
        class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded focus:outline-none focus:shadow-outline"
        type="submit">
        Sign In
      </button>
    </div>
  </form>
</template>
