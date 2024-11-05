<template>
  <h1 id="welcome-header" class="text-3xl text-white font-bold tracking-wider text-shadow mb-4 text-center"
    data-value="Mateusz Krasiński">
    Mateusz Krasiński
  </h1>
  <h2 id="q-header" class="text-sm text-white font-bold tracking-wider text-shadow mb-8 text-center"
    data-value="Software Developer & Computer Science Engineer">
    Software Developer & Computer Science Engineer
</h2>
  <ripple-button id="ripple-button" class="items-center shadow-2xl" :message="contactMessage"></ripple-button>
</template>


<script>
import RippleButton from "./RippleButton.vue";

export default {
  name: "RegularWelcomeComponent",
  components: {
    RippleButton
  },
  data() {
    return {
      contactMessage: "Let's stay in touch",

    }
  },
  methods: {
    randomizeText(curr) {
      let iteration = 0;
      const originalText = curr.dataset.value;
      const interval = setInterval(() => {
        curr.innerText = originalText
          .split("")
          .map((letter, index) => {
            if (index < iteration) {
              return originalText[index];
            }
            if (letter === " ") return " ";
            if (letter.toLowerCase() === letter)
              return this.lowerCaseLetters[Math.floor(Math.random() * 26)];
            else if (letter.toUpperCase() === letter)
              return this.upperCaseLetters[Math.floor(Math.random() * 26)];
          })
          .join("");

        if (iteration >= originalText.length) clearInterval(interval);

        iteration += 1;
      }, 20);
    }
  },

  mounted() {
    this.upperCaseLetters = "ABCDEFGHIJKLMNOPQRSTUVWXYZ"
    this.lowerCaseLetters = this.upperCaseLetters.toLowerCase();
    let header = document.getElementById("q-header")
    this.randomizeText(header); 
  }
}
</script>

<style scoped>
.custom-slide {
  text-align: center;
  justify-content: center;
  justify-items: center;
  padding: 10%;
}

.text-shadow {
  text-shadow: rgb(0, 0, 0) 1px 0 10px;
}

</style>