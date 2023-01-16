<template>
  <nav class="scrim-bg absolute z-40 home-header top-0 left-0 text-center" aria-label="Main Menu">
    <nuxt-link class="font-primary text-6xl lowercase text-black mb-6 block" to="/">
        Gary Abbott
    </nuxt-link>
    <ul class="flex">
      <li class="flex-1 text-center">
        <nuxt-link class="font-primary" to="/about">About</nuxt-link>
      </li>
      <li class="flex-1 ml-2">
        <nuxt-link class="font-primary" to="/choreography">Choreography</nuxt-link>
      </li>
      <li class="flex-1 ml-2">
        <nuxt-link class="font-primary" to="/contact">Contact</nuxt-link>
      </li>
    </ul>
  </nav>
</template>
  
  <script>
export default {
  name: 'HomeHeader',
}
</script>
  
  <style lang="postcss" scoped>
</style>
  