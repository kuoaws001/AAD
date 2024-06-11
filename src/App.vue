<template>
  <!-- menu -->
  <nav>
    <router-link to="/">Home</router-link>
    <template v-if="auth.account">
      <router-link to="/user">User</router-link>
      <router-link to="/logout">Logout</router-link>
    </template>
  </nav>

  <!-- view -->
  <main>
    <RouterView />
  </main>

  <!-- error -->
  <div id="error" v-if="auth.error">{{ auth.error }}</div>
</template>

<script lang="ts" setup>
import { RouterLink, RouterView } from 'vue-router'
import { auth } from '@/stores/auth'
</script>
