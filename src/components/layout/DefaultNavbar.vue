<template>
  <header
    class="backdrop-blur-xl bg-black/15 text-gray-100 py-4 px-6 shadow md:flex left-1/4 nav-bar w-1/2 z-10 mb-15 duration-300 ease-in rounded-3xl mt-2"
    :style="{ top: navbarPosition }"
  >
    <a href="#welcome" class="flex items-center cursor-pointer">
      <img class=" mr-2 w-1/7 min-w-12" :src="logo" />
      <h1 class="text-xl ">Mateusz Krasiński</h1>
    </a>
    <span
      @click="menuOpen"
      class="my-auto absolute right-6 top-8 text-3xl xl:hidden"
    >
      <i :class="[isOpen ? 'bi bi-x' : 'bi bi-list']"></i>
    </span>
    <div :class="['', isOpen ? '' : 'hidden xl:flex']">
      <div
        v-for="item in links"
        :key="item"
        class="ml-auto my-auto mr-2 p-2 rounded-xl"
      >
        <a v-if="item.name != 'Contact'" :href="item.link">{{ item.name }}</a>
        <a v-else :href="item.link"><i class="bi bi-envelope-fill cursor-pointer text-2xl" ></i></a>
      </div>
    </div>
  </header>
</template>

<script>
import logoPhoto from "@/assets/logo.svg";
// import kaggleIcon from "@/assets/logos/kaggle-icon.svg"

export default {
  name: "DefaultNavbar",
  data() {
    return {
      logo: logoPhoto,
      links: [
        { name: "Career Path", link: "#careerPath" },
        { name: "Projects", link: "#projects" },
        { name: "Skills and Technologies", link: "#skills" },
        { name: "Contact", link: "#contact" },
      ],
      isOpen: false,
      isNavbarHidden: false,
      prevScrollPos: 0,
    };
  },
  computed: {
    navbarPosition() {
      return this.isNavbarHidden ? "-100px" : "0";
    },
  },
  mounted() {
    window.addEventListener("scroll", this.handleScroll);
  },
  methods: {
    menuOpen() {
      this.isOpen = !this.isOpen;
    },
    handleScroll() {
      const currentScrollPos = window.scrollY;
      this.isNavbarHidden = currentScrollPos > this.prevScrollPos;
      this.prevScrollPos = currentScrollPos;
    },
  },
  beforeUnmount() {
    window.removeEventListener("scroll", this.handleScroll);
  },
};
</script>

<style scoped>
.nav-bar {
  position: fixed;
}

.language-selector {
  margin-right: 10px;
}


@media (min-width: 1160) {
  .xl\:hidden {
    display: none;
  }
  .xl\:flex {
    display: flex;
  }
  .xl\:my-0 {
    margin-top: 0px;
    margin-bottom: 0px;
  }
}

</style>