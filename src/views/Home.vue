<template>
    <div class="home">
    	<!-- Landing Carousel -->
        <LandingCarousel />
        <!-- Categories -->
        <LandingCategories />
        <!-- Store Overview -->
        <StoreOverview />
    </div>
</template>
<script>
// @ is an alias to /src
import LandingCarousel from "@/components/LandingCarousel.vue";
import LandingCategories from "@/components/LandingCategories.vue";
import StoreOverview from "@/components/StoreOverview.vue";

export default {
    name: "home",
    components: {
        LandingCarousel,
        LandingCategories,
        StoreOverview
    }
};
</script>