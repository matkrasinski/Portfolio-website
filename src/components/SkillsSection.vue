<template>
    <div id="skills" class="container text-center w-full bg-white rounded-3xl shadow-2xl">
        <h1
            class=" text-center mb-16 text-6xl font-manrope font-black leading-snug text-transparent bg-clip-text bg-gradient-to-r from-indigo-600 via-pink-600 to-purple-600">
            Skills and Technologies</h1>

        <div v-for="(technologies, i) in technologiesLists" :key="i">
            <div v-for="(technology, i) in technologies" :key="i" :style="{ animationDelay: `${getRandomDelay()}s` }"
                class="floating inline-block m-8 p-8  border-4 rounded-3xl w-32 h-32 hover-gray">
                <img :src="technology.logo">
                <!-- <a class="text-sm">{{ technology.name }}</a> -->
            </div>
        </div>
    </div>
</template>

<script>
import pythonLogo from "@/assets/logos/python-logo.png"
import javaLogo from "@/assets/logos/java-logo.png"
import javaScriptLogo from "@/assets/logos/javascript-logo.png"
import dockerLogo from "@/assets/logos/docker-logo.png"
import sklearnLogo from "@/assets/logos/scikit_learn-logo.png"

import vueLogo from "@/assets/logos/vue-logo.png"
import springLogo from "@/assets/logos/spring-logo.png"
import postgresqlLogo from "@/assets/logos/postgresql-logo.png"
import mysqlLogo from "@/assets/logos/mysql-logo.png"
import mongodbLogo from "@/assets/logos/mongodb-logo.png"


import gitLogo from "@/assets/logos/git-logo.png"
import githubLogo from "@/assets/logos/github-logo.png"
import bitbucketLogo from "@/assets/logos/bitbucket-logo.png"


export default {

    data() {
        return {
            technologiesLists: [
                [
                    { logo: pythonLogo, name: "Python" },
                    { logo: javaLogo, name: "Java" },
                    { logo: javaScriptLogo, name: "JavaScript" },
                    { logo: dockerLogo, name: "Docker" },
                    { logo: sklearnLogo, name: "Scikit-Learn" }
                ],
                [
                    { logo: vueLogo, name: "Vue.js" },
                    { logo: springLogo, name: "Spring" },
                    { logo: gitLogo, name: "Git" },
                    { logo: githubLogo, name: "GitHub" },
                    { logo: bitbucketLogo, name: "Bitbucket" }
                ],
                [
                    { logo: postgresqlLogo, name: "PostgreSQL" },
                    { logo: mysqlLogo, name: "MySQL" },
                    { logo: mongodbLogo, name: "MongoDB" }
                ]
            ]

        }
    },
    methods: {
        getRandomDelay() {
            return (Math.random() * 2).toFixed(2);
        },
    },
};
</script>

<style scoped>
@keyframes float {

    0%,
    100% {
        transform: translateY(0);
    }

    50% {
        transform: translateY(-35px);
    }
}

.floating {
    animation: float 4s ease-in-out infinite;
}

.hover-gray img {
    transition: filter 0.3s ease;
}

.hover-gray img:hover {
    filter: grayscale(100%);
}
</style>
