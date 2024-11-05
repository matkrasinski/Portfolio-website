<template>
  <h1 id="welcome-header" class="text-7xl text-white font-bold tracking-wider text-shadow mb-4 text-center"
    data-value="Mateusz Krasiński">
    Mateusz Krasiński
  </h1>
  <h2 id="q-header" class="text-2xl text-white font-bold tracking-wider text-shadow mb-8 text-center"
    data-value="Software Developer & Computer Science Engineer">
    Software Developer & Computer Science Engineer
  </h2>

  <ripple-button id="ripple-button" class="items-center shadow-2xl" :message="contactMessage"></ripple-button>
  <div class="desc-box p-8">
    <div class="logo-details justify-center">
      <div class="media-icons">
        <a href="#"><i class="bi bi-linkedin"></i></a>
        <a href="#"><i class="bi bi-github"></i></a>
        <img class="inline-block cursor-pointer mb-2 mx-2" src="@/assets/logos/kaggle-icon.svg">
        <a id="mail" @click="copyToClipboard()" href="#"><i class="bi bi-envelope"></i></a>
      </div>
    </div>
  </div>
</template>

<script>
import RippleButton from "./RippleButton.vue";

export default {
  name: "RegularWelcomeComponent",
  components: {
    RippleButton,
  },
  data() {
    return {
      contactMessage: "Get in touch",
      upperCaseLetters: null,
      lowerCaseLetters: null,
    };
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
    },
    copyToClipboard() {
      const emailAddress = "mat.krasinski@gmail.com"

      navigator.clipboard.writeText(emailAddress);
    
      alert("Copied my email address: " + emailAddress);
    }
  },

  mounted() {
    this.upperCaseLetters = "ABCDEFGHIJKLMNOPQRSTUVWXYZ";
    this.lowerCaseLetters = this.upperCaseLetters.toLowerCase();
    let header = document.getElementById("q-header");
    this.randomizeText(header);
  },
};
</script>

<style scoped>
.text-shadow {
  text-shadow: rgb(0, 0, 0) 1px 0 10px;
}

h2 {
  font-family: "SF Mono", SFMono-Regular, ui-monospace, "DejaVu Sans Mono",
    Menlo, Consolas, monospace;
  font-weight: lighter;
}



.media-icons a {
  height: 40px;
  width: 40px;
  margin: 0 8px;
  text-align: center;
  line-height: 40px;
  color: #fff;
  font-size: 17px;
  
  display: inline-block;
  margin-right: 2rem;
}

.media-icons  img {
  height: 40px;
  width: 40px;
  color: #fff;
  padding: 8px;
}


.media-icons  img {
  height: 40px;
  width: 40px;
  border-radius: 50%;
}
</style>
