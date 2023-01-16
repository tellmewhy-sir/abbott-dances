<template>
  <div class="bg-burgundy w-full">

    <main>
      <section class="w-full p-8">
        <h1 class="font-primary text-5xl text-gray-100">About</h1>
        <p>{{ bio }}</p>
        <p>{{ artisticStatement }}</p>
      </section>
    </main>
  </div>
  </template>
  <script>
  export default {
    async asyncData({ $content, error }) {
      let bio, artisticStatement;
      try {
        const [info] = await $content("about").fetch();
        bio = info.bio
        artisticStatement = info.artiststatement
      } catch (e) {
        error({ message: "About page content not found" });
      }
      return { 
        bio,
        artisticStatement
       };
    },
  }
  </script>
  