<!-- mini card auto -->
<script>

    export default {
        name: 'MiniCardAuto',

        props: {
            // array of img and type of car and the reuslt of search
            TypeCar: {
                type: Array,
                default: () => [
                    { image: '/src/assets/AutoCar Projcet Asset/imgs/assets/cabrio.jpg', type: 'Cabrio', result: '3' },
                    { image: '/src/assets/AutoCar Projcet Asset/imgs/assets/coupe.jpg', type: 'Coupe', result: '0' },
                    { image: '/src/assets/AutoCar Projcet Asset/imgs/assets/hatchback.jpg', type: 'Hatchback', result: '2' },
                    { image: '/src/assets/AutoCar Projcet Asset/imgs/assets/pickup.jpg', type: 'Pick Up', result: '0' },
                    { image: '/src/assets/AutoCar Projcet Asset/imgs/assets/sedan.jpg', type: 'Sedan', result: '3' },
                    { image: '/src/assets/AutoCar Projcet Asset/imgs/assets/suv.jpg', type: 'SUV', result: '4' },
                ],
            }
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

    <!-- mini card auto -->
    <div class="mini-card-auto">
        <div class="mini-card-auto-container">
            <div class="mini-card-auto-container-item" v-for="car in TypeCar" :key="car.type">
                <img :src="car.image" alt="car image">
                <div class="mini-card-auto-container-item-content">
                    <h1>{{ car.type }}</h1>
                    <p>{{ car.result }} Results</p>
                </div>
            </div>
        </div>
    </div>

</template>

<!-- style -->
<style lang="scss" scoped>

@use '../styles/partials/_variables' as *;

.mini-card-auto {
    max-width: 140rem;
    margin: 3.125rem auto;

    .mini-card-auto-container {
        display: flex;

        .mini-card-auto-container-item {
            box-shadow: 0 0.625rem 1.875rem rgba(0, 0, 0, 0.1);
            width: calc(100% / 6);
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            gap: 1rem;
            padding: 1.875rem 0;
            cursor: pointer;

            &:hover {
                box-shadow: 0 0.625rem 1.875rem rgba(0, 0, 0, 0.2);
            }
    
            img {   
                object-fit: cover;
            }

            .mini-card-auto-container-item-content {
                h1 {
                    font-size: 1.5rem;
                    font-weight: 700;
                    color: $color-secondary;
                    text-align: center;
                }

                p {
                    font-size: 1.125rem;
                    font-weight: 400;
                    color: $color-secondary;
                    text-align: center;
                }
            }
        }
    }
}

</style>