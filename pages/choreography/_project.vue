<template>
  <main class="bg-amber items-center md:h-screen overflow-y-scroll pt-20 md:pt-10">
    <section v-if="post">
      <nav class="mb-8 text-center" aria-label="go back">
        <router-back class="block" />
      </nav>

      <article>
        <!-- <div class="md:grid grid--choreography mb-8"> -->
        <div class="flex flex-col items-center mb-8 md:px-48">
          <div>
            <h1 class="font-primary text-center">{{ post.title }} ({{ post.year }})</h1>
            <p class="mt-1 mb-8 text-brown text-center">{{ post.description }}</p>
          </div>
          <div class="px-12 text-brown project__content">
            <nuxt-content :document="post" />
          </div>
        </div>
        <img
          v-if="post.cover"
          class="cover-image"
          :src="post.cover"
        >
        <!-- <h6 class="inline py-1 px-2 mr-1 bg-gray text-white text-sm font-medium rounded-sm">{{ post.category }}</h6> -->
        <div v-if="post.gallery" class="nuxt-content">
          <img
            v-for="image in post.gallery"
            class="image"
            :key="image.id"
            :src="image"
          >
        </div>
      </article>
    </section>
  </main>
</template>

<script>
export default {
  async asyncData({ $content, params, error }) {
    let post;
    try {
      post = await $content("projects", params.project).fetch();
    } catch (e) {
      error({ message: "Project not found" });
    }
    return { post };
  },
}
</script>
<style scoped>
.project__content p {
  color: #531818
}
</style>
