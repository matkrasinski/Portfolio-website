<template>
    <button class="btn-ripple rounded-3xl p-2">
        {{ this.$props.message }}
    </button>
</template>

<script>
export default {
    name: "RippleButton",
    props:["message"]
}
</script>

<style scoped>

.btn-ripple {
    border: none;
    outline: none;
    background-color: rgb(128, 0, 128); /* Purple base color */
    color: #fff;
    place-items: center;
    font-size: 18px;
    cursor: pointer;
    border: 2px solid rgb(128, 0, 128); /* Purple border */

    animation-name: ripple;
    animation-duration: 3s;
    animation-iteration-count: infinite;
    animation-fill-mode: both;
}


@keyframes ripple {
    0% {
        box-shadow: 0 0 0 0 rgba(186, 85, 211, 0.4), 0 0 0 0 rgba(148, 0, 211, 0.4);
    }
    80% {
        box-shadow: 0 0 0 20px rgba(186, 85, 211, 0), 0 0 0 40px rgba(148, 0, 211, 0);
    }
    100% {
        box-shadow: 0 0 0 0 rgba(186, 85, 211, 0), 0 0 0 0 rgba(148, 0, 211, 0);
    }
}
</style>