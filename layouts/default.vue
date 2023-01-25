
import SiteMenu from '~/components/global/SiteMenu.vue';

<template>
  <div class="wrapper" :class="{ 'bg-amber': isProjectPage }">
    <Header v-if="!isHome" class="md:hidden" @open="showMenu = true" />
    <nuxt v-if="isHome" />
    <div v-else class="relative w-full" :class="{ 'md:grid grid--page': isProjectPage }">
      <aside class="site-menu z-20 p-8 left-10 top-10 hidden md:block" :class="{ 'absolute': !isProjectPage }">
        <SiteMenu />
      </aside>
      <nuxt />
    </div>
    <aside v-if="showMenu" class="site-menu z-20 p-8 absolute left-0 top-0 right-0 bottom-0 bg-white text-center">
      <button class="button p-4" @click="showMenu = false">
        <font-awesome-icon icon="fa fa-times" size="xl" />
      </button>
      <SiteMenu @close="showMenu = false" />
    </aside>
    <!-- <ColorModePicker /> -->
  </div>
</template>

<script>
export default {
  data() {
    return {
      showMenu: false,
    }
  },

  computed: {
    isHome() {
      return this.$nuxt.$route.path === '/'
    },
    isProjectPage() {
      return this.$nuxt.$route.params.project
    }
  },
}
</script>
