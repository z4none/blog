<script setup lang="ts">
import { computed, reactive } from 'vue'
import { useHead } from '@vueuse/head'

const siteData = reactive({
  title: 'My website',
  description: 'My beautiful website',
})
useHead({
  title: computed(() => siteData.title),
  meta: [
    {
      name: 'description',
      content: computed(() => siteData.description),
    },
  ],
})
</script>

<template>
  <div class="text-center">
    <router-link to="/">
      Home
    </router-link> |
    <router-link to="/user">
      User
    </router-link> |
    <router-link to="/user/xxx">
      User - xxx
    </router-link> |
    <router-link to="/deep/post">
      Deep post
    </router-link> |
    <router-link to="/about">
      About
    </router-link>
    <div class="m-6">
      <router-view />
    </div>
  </div>
</template>
