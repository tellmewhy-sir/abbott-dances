<template>
  <div class="w-full about-page relative">
    <div class="bg-burgundy absolute top-0 left-0 right-0 bottom-0 opacity-90 h-screen"></div>
    <main class="w-full text-white avenir z-10 relative">
      <div class="about-page__content h-screen overflow-y-scroll">
        <section class="mb-12">
          <h1 class="font-primary text-5xl text-gray-100 mb-8">About</h1>
          <h2 class="font-primary text-3xl text-gray-100 mb-8">Bio</h2>
          <p class="text-white font-primary text-2xl">
            {{ bio }}
          </p>
        </section>
        <section>
          <h2 class="font-primary text-3xl text-gray-100 mb-8">Artistic Statement</h2>
          <p class="text-white font-primary text-2xl">{{ artisticStatement }}</p>
        </section>
        <div class="h-screen"></div>
      </div>
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
<style scoped>
.about-page {
  background-image: url(../../assets/images/gary-bulgaria.jpg);
  background-size: cover;
  background-position: top;
}

.about-page__content {
  width: 100%;
  max-width: 800px;
  margin-top: 0;
  margin-left: auto;
  margin-bottom: 0;
  padding: 5rem 2rem;}

@media (min-width: 900px) {
  .about-page__content p {
    line-height: 5.75rem;
  }
}
</style>
  