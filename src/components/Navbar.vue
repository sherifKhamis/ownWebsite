<template>
    <nav class="fixed top-0 left-0 w-full bg-white text-black shadow-md p-4 z-50 transition duration-300" :class="{ 'shadow-none': atTop }">
      <div class="max-w-6xl mx-auto flex justify-between items-center">
        <div class="text-xl font-bold">
          <a href="#" class="text-black px-4 py-2 rounded-md transition duration-300 hover:bg-black hover:text-white">Sherif Khamis | Informatiker</a>
        </div>
        <div class="flex space-x-6">
          <a href="#Über mich" class="text-black px-4 py-2 rounded-md transition duration-300 hover:bg-black hover:text-white">Über mich</a>
          <a href="#Qualifikation" class="text-black px-4 py-2 rounded-md transition duration-300 hover:bg-black hover:text-white">Qualifikation</a>
          <a href="#" class="text-black px-4 py-2 rounded-md transition duration-300 hover:bg-black hover:text-white">Projekte</a>
        </div>
      </div>
    </nav>
  </template>
  
  <script>
  export default {
    name: "Navbar",
    data() {
      return {
        atTop: true,
      };
    },
    mounted() {
      window.addEventListener("scroll", this.handleScroll);
    },
    beforeUnmount() {
      window.removeEventListener("scroll", this.handleScroll);
    },
    methods: {
      handleScroll() {
        this.atTop = window.scrollY === 0;
      },
    },
  };
  </script>
  