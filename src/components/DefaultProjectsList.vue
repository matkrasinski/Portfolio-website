<template>
    <div id="projectList" class="flex flex-col bg-gray-300 pt-16 shadow-2xl">
        <h1
            class="pb-8 text-center text-6xl font-manrope font-black leading-snug text-transparent bg-clip-text bg-gradient-to-r from-indigo-600 via-pink-600 to-purple-600">
            Projects
        </h1>
        <div class="w-full draggable container flex flex-col items-center gap-16 pb-32">
            <div class="grid w-full grid-cols-1 gap-6 md:grid-cols-2 lg:grid-cols-3">
                <project-item v-for="item in projectList" :key="item" :item="item"></project-item>
            </div>
        </div>
    </div>
</template>

<script>
import ProjectItem from "./ProjectItem.vue";

export default {
    name: "DefaultProjectsList",
    props: ["projectList"],
    components: {
        ProjectItem,
    },
};
</script>

<style scoped></style>
