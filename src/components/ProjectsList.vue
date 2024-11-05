<template>
    <div id="projects">

        <default-projects-list v-if="isDefault"    
        :projectList="projectList"
        />
        <carousel-projects-list v-else 
        :projectList="projectList" 
        />
    </div>
</template>

<script>
import DefaultProjectsList from './DefaultProjectsList.vue'
import CarouselProjectsList from './CarouselProjectList.vue'

import filmscore from "@/assets/projects/filmscore.png"
import flightsSummary from "@/assets/projects/flights-summary.png"
import eDrivingSchool from "@/assets/projects/e-driving-school.png"
import adoto from "@/assets/projects/adoto.png"
import whatTheyMean from "@/assets/projects/what-they-mean.png"
import opinionCollector from "@/assets/projects/opinion-collector.png"


export default {
    name: 'ProjectsList',
    components: {
        DefaultProjectsList,
        CarouselProjectsList
    },
    data() {
        return {
            projectList: [
                {image : filmscore},
                {image : flightsSummary},
                {image : eDrivingSchool},
                {image : adoto},
                {image : whatTheyMean},
                {image : opinionCollector},
            ],
            isDefault: true
        }
    },
    mounted() {
        this.checkSize();
        window.addEventListener('resize', this.checkSize)
    }, 
    methods: {
        checkSize() {
            this.isDefault = window.innerWidth > 900;
        }
    },
    beforeUnmount() {
        window.removeEventListener("resize", this.handleScroll);
    }
}


</script>

<style scoped>

.price-container {
    width: 66%;
}

@media screen and (max-width: 520px) {
    .price-container {
        width: 90%;
    }
}

</style>