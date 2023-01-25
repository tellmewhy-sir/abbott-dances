<template>
  <nav class="mt-10 md:mt-0 md:absolute z-40 home-header md:top-10 md:left-10 text-center" aria-label="Main Menu">
    <nuxt-link class="font-primary text-6xl lowercase text-black mb-6 block" to="/">
        Gary Abbott
    </nuxt-link>
    <ul class="flex">
      <li class="flex-1 text-center">
        <nuxt-link class="font-primary" to="/about" @click="$emit('close')">About</nuxt-link>
      </li>
      <li class="flex-1 ml-2">
        <nuxt-link class="font-primary" to="/choreography" @click="$emit('close')">Choreography</nuxt-link>
      </li>
      <li class="flex-1 ml-2">
        <!-- <nuxt-link class="font-primary" to="/contact">Contact</nuxt-link> -->
        <a class="font-primary" href="mailto:garyabbott56@gmail.com">Contact</a>
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
  