<template>
  <nav class="w-full dark:bg-black dark:text-white flex flex-col md:flex-row items-center md:justify-between px-6 py-4 border-b border-b-gray-60 shadow-sm max-w-screen-2xl mx-auto"
    >
    <ul class="flex">
      <li class="flex-1">
        <nuxt-link
        class="font-semibold tracking-tight block cursor-pointer p-2 hover:text-blue-500 transition-colors duration-300"
        to="/">Home</nuxt-link>
      </li>
      <li class="flex-1 ml-2">
        <nuxt-link
        class="font-semibold tracking-tight block cursor-pointer p-2 hover:text-blue-500 transition-colors duration-300"
         to="/about">About</nuxt-link>
      </li>
      <li class="flex-1 ml-2">
        <nuxt-link
        class="font-semibold tracking-tight block cursor-pointer p-2 hover:text-blue-500 transition-colors duration-300"
         to="/blog">Blog</nuxt-link>
      </li>
      <li class="flex-1 ml-2">
        <nuxt-link
        class="font-semibold tracking-tight block cursor-pointer p-2 hover:text-blue-500 transition-colors duration-300"
        to="/projects">Projects</nuxt-link>
      </li>
    </ul>
  </nav>
</template>

<script>
export default {
  name: 'Header'
}
</script>

<style lang="postcss" scoped>
.scrim-bg {
  &::before {
    content: '';
    z-index: -1;
    background-color: var(--bg);
    @apply absolute bottom-0 inset-x-0 h-12 mb-4 transition-colors duration-200 ease-in-out;
  }
  &::after {
    content: '';
    z-index: -1;
    opacity: 1;
    animation: fadeIn1 500ms ease-in-out;
    @apply pointer-events-none absolute bottom-0 inset-x-0 h-16 -mb-12;
    background: linear-gradient(to bottom, #111827, cubic-bezier(0.15, 0, 0.45, 1), transparent);
  }
}
.nuxt-link-exact-active {
  @apply text-gray-200 border-gray-400 bg-gray-800 bg-opacity-25 cursor-default;
}

.light {
  & .scrim-bg {
    &::after {
      animation-name: fadeIn2;
      background: linear-gradient(to bottom, #e5e7eb, cubic-bezier(0.15, 0, 0.45, 1), transparent);
    }
  }
  & .nuxt-link-exact-active {
    @apply text-primary-700 border-gray-600 bg-gray-100;
  }
}

/* Need two because of smoother switching between color modes */
@keyframes fadeIn1 {
  from { opacity: 0; }
  to { opacity: 1; }
}
@keyframes fadeIn2 {
  from { opacity: 0; }
  to { opacity: 1; }
}
</style>
