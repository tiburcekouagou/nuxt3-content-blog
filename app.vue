<template>
  <div class="max-w-3xl px-4 mx-auto">
    <!-- Header -->
    <header class="mt-8 mb-4 flex justify-between items-c">
      <div>
        <h1 class="text-2xl font-semibold">
          <NuxtLink to="/">Personal Blog</NuxtLink>
        </h1>
        <p class="text-gray-500">Learn programming easily !</p>
      </div>

      <Btn>Hire Me</Btn>
    </header>
    <!-- ./ Header -->

    <!-- Main Content -->
    <NuxtPage />
    <!-- ./ Main Content -->
  </div>
</template>

<style>
body {
  @apply bg-gray-100
}
</style>
