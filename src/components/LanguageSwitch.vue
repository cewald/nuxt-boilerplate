<script setup>
const { locale, locales } = useI18n()
const switchLocalePath = useSwitchLocalePath()
</script>3

<template>
  <div class="flex gap-2 font-mono text-xs uppercase">
    <template
      v-for="l in locales"
      :key="l.code"
    >
      <NuxtLink
        v-if="l.code !== locale"
        :to="switchLocalePath(l.code)"
      >
        {{ l.name }}
      </NuxtLink>
      <span
        v-else
        class="underline"
      >{{ l.name }}</span>
    </template>
  </div>
</template>
