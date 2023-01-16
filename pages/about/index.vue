<template>
  <div class="bg-burgundy w-full">

    <main>
      <section class="w-full p-8">
        <h1 class="font-primary text-5xl text-gray-100">About</h1>
        <p>{{ info }}</p>
        <!-- <p>{{ info.artiststatement }}</p> -->
      </section>
    </main>
  </div>
  </template>
  <script>
  export default {
    async asyncData({ $content, error }) {
      let info;
      try {
        info = await $content("about").fetch();
        console.log(info);
      } catch (e) {
        error({ message: "About page content not found" });
      }
      return { info };
    },
  }
  </script>
  