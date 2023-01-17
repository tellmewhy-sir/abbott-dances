<template>
  <div class="bg-burgundy w-full">
    <main class="w-full p-8 text-white avenir">
      <nav class="mb-8 z-40" aria-label="go back">
        <router-back class="block" />
      </nav>
      <section class="mb-12">
        <h1 class="font-primary text-5xl text-gray-100 mb-8">About</h1>
        <h2 class="font-primary text-3xl text-gray-100 mb-8">Bio</h2>
        <p class="text-white">
          {{ bio }}
        </p>
      </section>
      <section>
        <h2 class="font-primary text-3xl text-gray-100 mb-8">Artistic Statement</h2>
        <p class="text-white">{{ artisticStatement }}</p>
      </section>
    </main>
  </div>
</template>
  <script>
export default {
  async asyncData({ $content, error }) {
    let bio, artisticStatement
    try {
      const [info] = await $content('about').fetch()
      bio = info.bio
      artisticStatement = info.artiststatement
    } catch (e) {
      error({ message: 'About page content not found' })
    }
    return {
      bio,
      artisticStatement,
    }
  },
}
</script>
  