<template>
  <nav class="fixed top-0 left-0 w-full bg-white text-black shadow-md p-4 z-50 transition duration-300" :class="{ 'shadow-none': atTop }">
    <div class="max-w-6xl mx-auto flex justify-between items-center">
      <div class="text-xl font-bold">
        <a href="#" class="text-black px-4 py-2 rounded-md transition duration-300 hover:bg-black hover:text-white">
          Sherif Khamis | Informatiker
        </a>
      </div>
      <div class="flex space-x-6">
        <button @click="scrollToSection('ueber-mich')" class="text-black px-4 py-2 rounded-md transition duration-300 hover:bg-black hover:text-white">
          Über mich
        </button>
        <button @click="scrollToSection('qualifikation')" class="text-black px-4 py-2 rounded-md transition duration-300 hover:bg-black hover:text-white">
          Qualifikation
        </button>
        <button @click="scrollToSection('projekte')" class="text-black px-4 py-2 rounded-md transition duration-300 hover:bg-black hover:text-white">
          Projekte
        </button>
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
  unmounted() {
    window.removeEventListener("scroll", this.handleScroll);
  },
  methods: {
    handleScroll() {
      this.atTop = window.scrollY === 0;
    },
    scrollToSection(sectionId) {
      const section = document.getElementById(sectionId);
      if (section) {
        const offset = 100; // Abstand zur Navbar
        const sectionPosition = section.getBoundingClientRect().top + window.scrollY - offset;

        window.scrollTo({ top: sectionPosition, behavior: "smooth" });
      }
    }
  }
};
</script>
