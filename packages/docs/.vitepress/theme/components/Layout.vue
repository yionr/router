<script setup lang="ts">
import { watch } from 'vue'
import { useData } from 'vitepress'
import VPTheme from 'vitepress/theme'

const { frontmatter } = useData()

watch(() => frontmatter.value.dir, (dir = 'ltr') => {
  if (typeof document === 'undefined') { return }
  document.documentElement.dir = dir
  document.body.dir = dir
  document.body.style.direction = dir
}, { immediate: true })
</script>

<template>
  <VPTheme.Layout />
</template>
