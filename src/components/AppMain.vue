<!-- script -->
<script>

import SliderSection from './SliderSection.vue'
import searchCar from './searchCar.vue'
import MiniCardAuto from './MiniCardAuto.vue'
import AutoCard from './AutoCard.vue'
import SellingBuyCar from './SellingBuyCar.vue'
import Customer from './customer.vue'
import ResentArticles from './ResentArticles.vue'

    export default {
        name: 'AppMain',

        components: {
            SliderSection,
            searchCar,
            MiniCardAuto,
            AutoCard,
            SellingBuyCar,
            Customer,
            ResentArticles,
        },
        
        props: {
            
        },

        data () {
            return {
                //
            }
        },
    }

</script>

<!-- template -->
<template>
    <SliderSection />
    <searchCar />
    <MiniCardAuto />
    <AutoCard />
    <SellingBuyCar />
    <Customer />
    <ResentArticles />
</template>

<!-- style -->
<style lang="scss" scoped>

@use '../styles/partials/_variables' as *;

</style>