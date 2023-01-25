<template>
    <!-- <button class="button p-4" @click="$emit('close')">
        <font-awesome-icon icon="fa fa-times" size="xl"/>
    </button> -->
    <nav class="home-header" aria-label="Main Menu">
      <nuxt-link @click.native="$emit('close')" class="font-primary text-3xl lowercase text-black text-center md:text-left mt-8 mb-6 block" to="/">
        Gary Abbott
      </nuxt-link>
      <ul class="flex flex-col gap-2">
        <li>
          <nuxt-link @click.native="$emit('close')" class="font-primary md:text-white" to="/about">About</nuxt-link>
        </li>
        <li>
          <nuxt-link @click.native="$emit('close')" class="font-primary md:text-white" to="/choreography">Choreography</nuxt-link>
        </li>
        <li>
          <!-- <nuxt-link class="font-primary text-white" to="/contact">Contact</nuxt-link> -->
          <a class="font-primary" href="mailto:garyabbott56@gmail.com">Contact</a>
        </li>
      </ul>
    </nav>
</template>

<style>
</style>