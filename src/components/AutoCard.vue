<!-- card -->
<script>

    export default {
        name: 'AutoCard',

        props: {

            Card: {
                type: Array,
                default: () => [
                    { 
                        image: '/src/assets/AutoCar Projcet Asset/imgs/assets/bmw-8-series-convertible-technical-data-sp-desktop-400x300.jpg', 
                        name:'BMW M9',
                        type:'Cabrio', 
                        IconDollar:'/src/assets/AutoCar Projcet Asset/imgs/assets/free-fa-brands-400.svg-fonta.svg', 
                        price:'34.000', 
                        IconCar:'/src/assets/AutoCar Projcet Asset/imgs/assets/free-fa-regular-400.svg-fonta.svg',
                        brand:'BMW', 
                        IconFuel:'/Vite-Vue-Starter/src/assets/AutoCar Projcet Asset/imgs/assets/free-fa-solid-900.svg-fonta.svg',
                        FuelType:'Eletric',
                        IconHeart:'/Vite-Vue-Starter/src/assets/AutoCar Projcet Asset/imgs/assets/free-fa-v4deprecations.svg-fonta.svg',
                    },
                    { 
                        image: '/src/assets/AutoCar Projcet Asset/imgs/assets/bmw88-400x300.jpg', 
                        name:'BMW M8',
                        type:'Cabrio', 
                        IconDollar:'/src/assets/AutoCar Projcet Asset/imgs/assets/free-fa-brands-400.svg-fonta.svg', 
                        price:'34.000', 
                        IconCar:'/src/assets/AutoCar Projcet Asset/imgs/assets/free-fa-regular-400.svg-fonta.svg',
                        brand:'BMW', 
                        IconFuel:'/Vite-Vue-Starter/src/assets/AutoCar Projcet Asset/imgs/assets/free-fa-solid-900.svg-fonta.svg',
                        FuelType:'Diesel',
                        IconHeart:'/Vite-Vue-Starter/src/assets/AutoCar Projcet Asset/imgs/assets/free-fa-v4deprecations.svg-fonta.svg',
                    },
                    { 
                        image: '/src/assets/AutoCar Projcet Asset/imgs/assets/bmw442-400x300.jpg', 
                        name:'BMW 4',
                        type:'Cabrio', 
                        IconDollar:'/src/assets/AutoCar Projcet Asset/imgs/assets/free-fa-brands-400.svg-fonta.svg', 
                        price:'34.000', 
                        IconCar:'/src/assets/AutoCar Projcet Asset/imgs/assets/free-fa-regular-400.svg-fonta.svg',
                        brand:'BMW', 
                        IconFuel:'/Vite-Vue-Starter/src/assets/AutoCar Projcet Asset/imgs/assets/free-fa-solid-900.svg-fonta.svg',
                        FuelType:'Gasoline',
                        IconHeart:'/Vite-Vue-Starter/src/assets/AutoCar Projcet Asset/imgs/assets/free-fa-v4deprecations.svg-fonta.svg',
                    },
                    { 
                        image: '/src/assets/AutoCar Projcet Asset/imgs/assets/yeni-ibiza-2-400x300.jpg', 
                        name:'Seat Ibiza',
                        type:'HatchBack', 
                        IconDollar:'/src/assets/AutoCar Projcet Asset/imgs/assets/free-fa-brands-400.svg-fonta.svg', 
                        price:'27.000', 
                        IconCar:'/src/assets/AutoCar Projcet Asset/imgs/assets/free-fa-regular-400.svg-fonta.svg',
                        brand:'Seat', 
                        IconFuel:'/Vite-Vue-Starter/src/assets/AutoCar Projcet Asset/imgs/assets/free-fa-solid-900.svg-fonta.svg',
                        FuelType:'Eletric',
                        IconHeart:'/Vite-Vue-Starter/src/assets/AutoCar Projcet Asset/imgs/assets/free-fa-v4deprecations.svg-fonta.svg',
                    },
                    { 
                        image: '/src/assets/AutoCar Projcet Asset/imgs/assets/makyajli-2022-seat-arona-1-400x300.jpg', 
                        name:'Seat Arona',
                        type:'SUV', 
                        IconDollar:'/src/assets/AutoCar Projcet Asset/imgs/assets/free-fa-brands-400.svg-fonta.svg', 
                        price:'68.000', 
                        IconCar:'/src/assets/AutoCar Projcet Asset/imgs/assets/free-fa-regular-400.svg-fonta.svg',
                        brand:'Seat', 
                        IconFuel:'/Vite-Vue-Starter/src/assets/AutoCar Projcet Asset/imgs/assets/free-fa-solid-900.svg-fonta.svg',
                        FuelType:'Gasoline',
                        IconHeart:'/Vite-Vue-Starter/src/assets/AutoCar Projcet Asset/imgs/assets/free-fa-v4deprecations.svg-fonta.svg',
                    },
                    { 
                        image: '/src/assets/AutoCar Projcet Asset/imgs/assets/vw-taigo3832-400x300.jpg', 
                        name:'Volswagen Taigo',
                        type:'SUV', 
                        IconDollar:'/src/assets/AutoCar Projcet Asset/imgs/assets/free-fa-brands-400.svg-fonta.svg', 
                        price:'52.000', 
                        IconCar:'/src/assets/AutoCar Projcet Asset/imgs/assets/free-fa-regular-400.svg-fonta.svg',
                        brand:'Volswagen', 
                        IconFuel:'/Vite-Vue-Starter/src/assets/AutoCar Projcet Asset/imgs/assets/free-fa-solid-900.svg-fonta.svg',
                        FuelType:'Eletric',
                        IconHeart:'/Vite-Vue-Starter/src/assets/AutoCar Projcet Asset/imgs/assets/free-fa-v4deprecations.svg-fonta.svg',
                    },
                    { 
                        image: '/src/assets/AutoCar Projcet Asset/imgs/assets/2019-vw-t-cross-400x300.jpg', 
                        name:'Volswagen T-Cross',
                        type:'SUV', 
                        IconDollar:'/src/assets/AutoCar Projcet Asset/imgs/assets/free-fa-brands-400.svg-fonta.svg', 
                        price:'47.000', 
                        IconCar:'/src/assets/AutoCar Projcet Asset/imgs/assets/free-fa-regular-400.svg-fonta.svg',
                        brand:'Volswagen', 
                        IconFuel:'/Vite-Vue-Starter/src/assets/AutoCar Projcet Asset/imgs/assets/free-fa-solid-900.svg-fonta.svg',
                        FuelType:'Diesel',
                        IconHeart:'/Vite-Vue-Starter/src/assets/AutoCar Projcet Asset/imgs/assets/free-fa-v4deprecations.svg-fonta.svg',
                    },
                    { 
                        image: '/src/assets/AutoCar Projcet Asset/imgs/assets/volkswagen-passat-1280x720-1-400x300.jpg', 
                        name:'Volswagen Passat',
                        type:'Sedan', 
                        IconDollar:'/src/assets/AutoCar Projcet Asset/imgs/assets/free-fa-brands-400.svg-fonta.svg', 
                        price:'32.000', 
                        IconCar:'/src/assets/AutoCar Projcet Asset/imgs/assets/free-fa-regular-400.svg-fonta.svg',
                        brand:'Volswagen', 
                        IconFuel:'/Vite-Vue-Starter/src/assets/AutoCar Projcet Asset/imgs/assets/free-fa-solid-900.svg-fonta.svg',
                        FuelType:'Diesel',
                        IconHeart:'/Vite-Vue-Starter/src/assets/AutoCar Projcet Asset/imgs/assets/free-fa-v4deprecations.svg-fonta.svg',
                    },
                ]
            },
        },

        data () {
            return {
              
            }
        },

        methods: {
    
        },
    }

</script>

<!-- template -->
<template>

    <!-- card -->
    <div class="card">
        <div class="card-container">
            <div class="card-container-item" v-for="car in Card" :key="car.name">
                <div class="card-container-item-content">
                    <img :src="car.image" alt="car image">
                    <h1>{{ car.name }} <sapn class="fa-solid fa-circle-check"></sapn></h1>
                    <p>{{ car.type }}</p>
                    <div class="card-container-item-content-icons">
                        <div class="I-Inside">
                            <a class="fa-solid fa-dollar-sign"></a>
                            <p>{{ car.price }}</p>
                        </div>
                        <div class="I-Inside">
                            <a class="fa-solid fa-car"></a>
                            <p>{{ car.brand }}</p>
                        </div>
                        <div class="I-Inside">
                            <a class="fa-solid fa-gas-pump"></a>
                            <p>{{ car.FuelType }}</p>
                        </div>
                        <a class="fa-regular fa-heart"></a>
                    </div>
                </div>
            </div>
        </div>
        
    </div>

    <!-- button to see more cars -->
    <div class="button-to-see-more-cars">
        <button>Show All Cars</button>
    </div>

</template>

<!-- style -->
<style lang="scss" scoped>

@use '../styles/partials/_variables' as *;
@use '../styles/partials/_mixing' as *;

.card {
    max-width: 140rem;
    margin: 3.125rem auto;

    .card-container {
        display: flex;
        flex-wrap: wrap;

        .card-container-item {
            width: calc(100% / 4); 
            

            .card-container-item-content {
                box-shadow: 0 0.625rem 1.875rem rgba(0, 0, 0, 0.1);
                margin-bottom: 2rem;
                padding: 2rem;
                transition: all 0.3s ease-in-out;


                // hover 
                &:hover {
                    box-shadow: 0 0.625rem 1.875rem rgba(0, 0, 0, 0.2);
                    cursor: pointer;
                    background-color: $color-tertiary;
                }


                img {
                    width: 100%;
                    height: 20rem;
                    object-fit: cover;
                    
                }

                h1 {
                    font-size: 1.5rem;
                    font-weight: 700;
                    margin: 1rem 0;
                }

                p {
                    font-size: 1.2rem;
                    font-weight: 400;
                    margin: 1rem 0;
                }

                .card-container-item-content-icons {
                    display: flex;
                    align-items: center;
                    justify-content: space-between;
                    margin: 1rem 0;

                   .I-Inside {
                        display: flex;
                        align-items: center;
                        gap: 0.5rem;

                        a {
                            font-size: 1.2rem;
                            color: $color-primary;
                        }

                        p {
                            font-size: 1.2rem;
                            font-weight: 400;
                        }
                    }

                    a {
                        font-size: 1.2rem;
                        color: $color-primary;
                        transition: all 0.3s ease-in-out;
                        cursor: pointer;
                    }
                }
            }
        }
    }
}

.button-to-see-more-cars {
    display: flex;
    justify-content: center;
    margin: 2rem;

    button {
        padding: 2rem 2rem;
        border: none;
        background-color: $color-secondary;
        color: $color-white;
        font-size: 1.5rem;
        font-weight: 400;
        cursor: pointer;
        transition: all 0.3s ease-in-out;

        &:hover {
            background-color: $color-tertiary;
        }
    }
}

</style>