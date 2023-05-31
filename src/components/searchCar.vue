<!-- info for searching car with that caracteristics -->
<script>

    export default {
        name: 'searchCar',
        
        props: {
            // caracteristiche auto 
            autoCaracteristic : {
                type : Array,
                default: () => [
                    { title: 'KeyWords', },

                    { title: 'Location',},

                    { 
                        title: 'All Categories',
                        type: Array,
                        default: () => [
                            { title: 'All Categories', },
                            { title: 'Cabrio',},
                            { title: 'Coupe',},
                            { title: 'Hatchback',},
                            { title: 'Pick Up',},
                            { title: 'Sedan',},
                            { title: 'Suv',},
                        ],
                        
                    },
                    { 
                        title: 'Brand',
                        type: Array,
                        default: () => [
                            { title: 'BMW'},
                            { title: 'Seat'},
                            { title: 'Volswagen'},
                            { title: 'Skoda'},
                            { title: 'Audi'},
                            { title: 'Toyota'}
                        ],
                    },
                    { 
                        title: 'Fuel Type',
                        type: Array,
                        default: () => [
                            { title: 'Diesel'},
                            { title: 'Gasoline'},
                            { title: 'Electric'},
                            { title: 'Hybrid'},
                        ],
                    },
                    { 
                        title: 'Transmission',
                        type: Array,
                        default: () => [
                            { title: 'Automatic'},
                            { title: 'Manual'},
                        ],  
                    },
                    { 
                        title: 'status',
                        type: Array,
                        default: () => [
                            { title: 'New'},
                            { title: 'Used'},
                        ],
                    }, 

                    { title: 'Search',}
                ],
            }
        },

        data () {
            return {
                
            }
        },

        methods: {
            // 
        },
    }

</script>

<!-- template -->
<template>

    <!-- button for all the props  -->
    <div class="container">
        <div class="container-caract">
            <div class="container-caract-item" v-for="car in autoCaracteristic" :key="car.title">
                
                <h1>{{ car.title }}</h1>
               
            </div>
        </div>
    </div>


</template>

<!-- style -->
<style lang="scss" scoped> 

@use '../styles/partials/_variables' as *;
@use '../styles/partials/_mixing' as *;

.container {
    max-width: 140rem;
    margin: 3.125rem auto;


    .container-caract {
        display: flex;
        justify-content: space-between;
        align-items: center;
        text-align: center;
        gap: 1rem;

        .container-caract-item {
            width: 100%;
            border: 1px solid $color-black;
            border-radius: 0.8rem;
            padding: 3rem;
            cursor: pointer;

            &:hover {
                background-color: $color-secondary;
            }

            h1 {
                font-size: 1.5rem;
                font-weight: 700;
                color: $color-black;

                &:hover {
                    color: $color-white;
                }
            }
        }
    }
}

</style>