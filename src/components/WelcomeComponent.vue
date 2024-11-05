<template>
    <div id="welcome" class="shadow">
        <masked-image v-if="mobile" :photo="mobilePhoto" :isMobile="mobile"></masked-image>
        <masked-image v-else :photo="defaultPhoto" :isMobile="mobile"></masked-image>
    </div>
</template>

<script>
import MaskedImage from './MaskedImage.vue';
import mobilePhoto from '../assets/computer-background-mobile.png';
import defaultPhoto from '../assets/computer-background.png';

export default {
    name: 'WelcomeComponent',
    data() {
        return {
            mobile: false,
            renderComponent: true,
            mobilePhoto: mobilePhoto,
            defaultPhoto: defaultPhoto
        }
    },
    components: {
        MaskedImage
    },
    mounted() {
        this.checkSize();
        window.addEventListener('resize', this.checkSize)
    }, 
    methods: {
        checkSize() {
            this.mobile = window.innerWidth < 900;
        }
    },
    beforeUnmount() {
        window.removeEventListener("resize", this.handleScroll);
    }
}

</script>

