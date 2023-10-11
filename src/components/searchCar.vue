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
                        SelectOption : {
                            type: Array,
                            default: () => [
                                { option: 'All Categories', },
                                { option: 'Cabrio',},
                                { option: 'Coupe',},
                                { option: 'Hatchback',},
                                { option: 'Pick Up',},
                                { option: 'Sedan',},
                                { option: 'Suv',},
                            ],
                        },
                        
                    },
                    { 
                        title: 'Brand',
                        SelectOption : {
                            type: Array,
                            default: () => [
                                { option: 'BMW'},
                                { option: 'Seat'},
                                { option: 'Volswagen'},
                                { option: 'Skoda'},
                                { option: 'Audi'},
                                { option: 'Toyota'}
                            ],
                        },
                    },
                    { 
                        title: 'Fuel Type',
                        SelectOption: {
                            type: Array,
                            default: () => [
                                { option: 'Diesel'},
                                { option: 'Gasoline'},
                                { option: 'Electric'},
                                { option: 'Hybrid'},
                            ],
                        },
                    },
                    { 
                        title: 'Transmission',
                        SelectOption: {
                            type: Array,
                            default: () => [
                                { option: 'Automatic'},
                                { option: 'Manual'},
                            ],
                        },
                    },
                    { 
                        title: 'status',
                        SelectOption: {
                            type: Array,
                            default: () => [
                                { option: 'New'},
                                { option: 'Used'},
                            ],
                        },
                    }, 
                ],
            }
        },

        data() {
            return {
                
            }
        },

        methods: {
           
        },       
    }

</script>

<!-- template -->
<template>

    <!-- button for all the props  -->
    <div class="container" id="minicard">
        <div class="container-caract">
            <div class="container-caract-item" v-for="car in autoCaracteristic" :key="car.title">
                <h1>{{ car.title }}</h1>
                <span class="fa-solid fa-caret-down fa-sm" style="color: #a6a6a6;"></span>
            </div>
            <button class="btn-search-car">Search</button>
        </div>
    </div>


</template>

<!-- style -->
<style lang="scss" scoped> 

@use '../styles/partials/_variables' as *;

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
            height: 75px;
            border: 1px solid $color-black;
            border-radius: 0.8rem;
            padding: 2rem;
            cursor: pointer;
            transition: all 0.3s ease-in-out;
            display: flex;
            justify-content: center;
            align-items: center;
            text-align: center;

            h1 {
                width: 100%;
                height: 100%;
                font-size: 1.5rem;
                font-weight: 700;
                color: $color-black;
                display: flex;
                justify-content: center;    
                align-items: center;
                text-align: center;
            }

            span {
                position: absolute;
                right: 2rem;
                font-size: 1.5rem;
                font-weight: 700;
                color: $color-black;
                display: flex;
                justify-content: center;    
                align-items: center;
                text-align: center;
                position: relative;
            }
        }

        .btn-search-car {
            width: 100%;
            border: 1px solid $color-secondary;
            background-color: $color-secondary;
            color: $color-white;
            border-radius: 0.8rem;
            padding: 3rem;
            cursor: pointer;
            transition: all 0.3s ease-in-out;

            &:hover {
                background-color: $color-tertiary;
                border: 1px solid $color-tertiary;
                color: $color-secondary;
            }
        }
    }
}

</style>