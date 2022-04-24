<template>
  <main>
    <section class="self-center flex flex-col flex-1 items-center justify-center">
      <h1 class="title text-center">{{ about.title }}</h1>
      <nuxt-content :document="about" />
    </section>
  </main>
</template>

<script>
export default {
  async asyncData({ $content, error }) {
    let about;
    try {
      about = await $content("about").fetch();
    } catch (e) {
      error({ message: "About not found" });
    }
    return { about };
  },
}
</script>
