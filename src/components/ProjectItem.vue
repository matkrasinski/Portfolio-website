<template>
    <div class="bg-white flex flex-col items-center gap-3 px-8 py-10 m-0 rounded-3xl shadow-md h-full">
        <div class=" relative ">
            <div class="absolute top-2 right-2 flex space-x-2">
                <div class="bg-white rounded-full shadow-[0_4px_15px_rgba(0,0,0,0.3)] text-center items-center rounded-icon">
                    <i class="bi bi-github text-xl text-transparent bg-clip-text bg-gradient-to-br from-indigo-600 via-pink-600 to-purple-600"></i>
                </div>
                <div class="bg-white rounded-full shadow-[0_4px_15px_rgba(0,0,0,0.3)] text-center items-center rounded-icon">
                    <i class="bi bi-box-arrow-up-right text-xl  text-transparent bg-clip-text bg-gradient-to-br from-indigo-600 via-pink-600 to-purple-600"></i>
                </div>
            </div>
            <img class="rounded-3xl shadow-[0_4px_15px_rgba(0,0,0,0.3)]" :src="item.image" alt="https://placehold.co/600x400">
        </div>
        <p class="text-2xl font-medium my-2">{{ "<PROJECT TITLE>" }}</p>
        <p class="text-center text-gray-500 w-3/4">{{ "<ORIGIN> <YEAR>" }}</p>
        <p class="text-lg text-red-500 my-4">
            {{ "<SHORT DESCRIPTION>" }}
                <span class="text-red-500 font-bold text-4xl">{{ "<SMT>" }}</span>
        </p>

        <!-- <p v-for="b in this.$props.item.benefits" :key="b" class="text-center">
            <i class="bi bi-check2 text-red-500 mr-1 "></i>{{ b }}
        </p> -->
    </div>
</template>

<script>

export default {
    props: ["item"],
    mounted() {
        console.log(this.item)
    }
}

</script>
<style scoped>
.rounded-icon {
    padding-top: 2px /* 4px */;
    padding-bottom: 2px /* 4px */;
    padding-left: 4px /* 8px */;
    padding-right: 4px /* 8px */;
}


</style>