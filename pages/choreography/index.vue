<template>
  <main class="bg-amber relative">
    <nav class="mb-8 z-40" aria-label="go back">
      <router-back class="block" />
    </nav>
    <section v-if="posts" class="w-full max-w-5xl mx-auto">
      <div class="z-10 relative">
        <h1 class="font-primary text-center p-8 mb-12 text-5xl">Choreography</h1>
        <posts post-type="projects" :page="'choreography'" :amount="10" @set-video="handleSetVideo" />
      </div>
      <div class="z-0 absolute h-full w-full flex justify-center items-center top-0 left-0">
        <video v-if="showVideo" :src="showVideo" autoplay loop />
      </div>
    </section>
  </main>
</template>

<script>
export default {
  data() {
    return {
      showVideo: null,
    }
  },

  methods: {
    handleSetVideo(videoUrl) {
      this.showVideo = videoUrl
    },
  },

  async asyncData({ $content, error }) {
    let posts
    try {
      posts = await $content('projects').fetch()
    } catch (e) {
      error({ message: 'Projects not found' })
    }
    return { posts }
  },
}
</script>
