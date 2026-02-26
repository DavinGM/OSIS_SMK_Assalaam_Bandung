<script setup lang="ts">
const route = useRoute()

const items = computed(() => [{
  label: 'Docs',
  to: '/docs',
  active: route.path.startsWith('/docs')
}, {
  label: 'Kinerja',
  to: '/kinerja',
  active: route.path.startsWith('/kinerja')
}, {
  label: 'Blog',
  to: '/blog',
  active: route.path.startsWith('/blog')
}, {
  label: 'Sejarah',
  to: '/sejarah',
  active: route.path.startsWith('/sejarah')
}])
</script>

<template>
  <UHeader>
    <template #left>
      <NuxtLink to="/" class="flex items-center gap-2">
        <AppLogo class="w-auto h-6 shrink-0" />
        <span class="font-bold text-lg hidden sm:block">OSIS SMK Assalaam</span>
      </NuxtLink>
    </template>

    <UNavigationMenu
      :items="items"
      variant="link"
    />

    <template #right>
      <UColorModeButton />

      <UButton
        icon="i-lucide-log-in"
        color="neutral"
        variant="ghost"
        to="/login"
        class="lg:hidden"
      />

      <UButton
        label="Sign in"
        color="neutral"
        variant="outline"
        to="/login"
        class="hidden lg:inline-flex"
      />

      <UButton
        label="Sign up"
        color="neutral"
        trailing-icon="i-lucide-arrow-right"
        class="hidden lg:inline-flex"
        to="/signup"
      />
    </template>


    <template #body>
      <UNavigationMenu
        :items="items"
        orientation="vertical"
        class="-mx-2.5"
      />

      <USeparator class="my-6" />

      <UButton
        label="Sign in"
        color="neutral"
        variant="subtle"
        to="/login"
        block
        class="mb-3"
      />
      <UButton
        label="Sign up"
        color="neutral"
        to="/signup"
        block
      />
    </template>
  </UHeader>
</template>
