<script setup lang="ts">
// const online = useOnline()
const app = useAppStore()
</script>

<template>
  <div>
    <!-- <Logos mb-6 /> -->

    <h2 class="font-zmx my-4" text="dark:yellow 4xl">
      AI 春联
    </h2>

    <AiPrompt class="mb-4" />

    <Suspense>
      <ClientOnly>
        <SpringFestivalCouplets :couplets-data="app.coupletsData" />
        <!-- <PageView v-if="online" /> -->
        <!-- <div v-else text-gray:80>
          You're offline
        </div> -->
      </ClientOnly>
      <template #fallback>
        <div italic op50>
          <span animate-pulse>Loading...</span>
        </div>
      </template>
    </Suspense>

    <BaseFooter />
  </div>
</template>
