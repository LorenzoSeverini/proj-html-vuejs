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
                        price:'34.000', 
                        brand:'BMW', 
                        FuelType:'Eletric',
                    },
                    { 
                        image: '/src/assets/AutoCar Projcet Asset/imgs/assets/bmw88-400x300.jpg', 
                        name:'BMW M8',
                        type:'Cabrio',  
                        price:'34.000', 
                        brand:'BMW', 
                        FuelType:'Diesel',
                    },
                    { 
                        image: '/src/assets/AutoCar Projcet Asset/imgs/assets/bmw442-400x300.jpg', 
                        name:'BMW 4',
                        type:'Cabrio',  
                        price:'34.000', 
                        brand:'BMW', 
                        FuelType:'Gasoline',
                    },
                    { 
                        image: '/src/assets/AutoCar Projcet Asset/imgs/assets/yeni-ibiza-2-400x300.jpg', 
                        name:'Seat Ibiza',
                        type:'HatchBack',  
                        price:'27.000', 
                        brand:'Seat', 
                        FuelType:'Eletric',
                    },
                    { 
                        image: '/src/assets/AutoCar Projcet Asset/imgs/assets/makyajli-2022-seat-arona-1-400x300.jpg', 
                        name:'Seat Arona',
                        type:'SUV',  
                        price:'68.000', 
                        brand:'Seat', 
                        FuelType:'Gasoline',
                    },
                    { 
                        image: '/src/assets/AutoCar Projcet Asset/imgs/assets/vw-taigo3832-400x300.jpg', 
                        name:'Volswagen Taigo',
                        type:'SUV',  
                        price:'52.000', 
                        brand:'Volswagen', 
                        FuelType:'Eletric',
                    },
                    { 
                        image: '/src/assets/AutoCar Projcet Asset/imgs/assets/2019-vw-t-cross-400x300.jpg', 
                        name:'Volswagen T-Cross',
                        type:'SUV', 
                        price:'47.000', 
                        brand:'Volswagen', 
                        FuelType:'Diesel',
                    },
                    { 
                        image: '/src/assets/AutoCar Projcet Asset/imgs/assets/volkswagen-passat-1280x720-1-400x300.jpg', 
                        name:'Volswagen Passat',
                        type:'Sedan', 
                        price:'32.000', 
                        brand:'Volswagen', 
                        FuelType:'Diesel',
                        
                    },
                ]
            },

            card2: {
                type: Array,
                default: () => [
                    { 
                        image: '/src/assets/AutoCar Projcet Asset/imgs/assets/bmw-8-series-convertible-technical-data-sp-desktop-400x300.jpg', 
                        name:'BMW M9',
                        type:'Cabrio',  
                        price:'34.000', 
                        brand:'BMW', 
                        FuelType:'Eletric',
                    },
                    { 
                        image: '/src/assets/AutoCar Projcet Asset/imgs/assets/bmw88-400x300.jpg', 
                        name:'BMW M8',
                        type:'Cabrio',  
                        price:'34.000', 
                        brand:'BMW', 
                        FuelType:'Diesel',
                    },
                    { 
                        image: '/src/assets/AutoCar Projcet Asset/imgs/assets/bmw442-400x300.jpg', 
                        name:'BMW 4',
                        type:'Cabrio',  
                        price:'34.000', 
                        brand:'BMW', 
                        FuelType:'Gasoline',
                    },
                    { 
                        image: '/src/assets/AutoCar Projcet Asset/imgs/assets/yeni-ibiza-2-400x300.jpg', 
                        name:'Seat Ibiza',
                        type:'HatchBack',  
                        price:'27.000', 
                        brand:'Seat', 
                        FuelType:'Eletric',
                    },
                    { 
                        image: '/src/assets/AutoCar Projcet Asset/imgs/assets/makyajli-2022-seat-arona-1-400x300.jpg', 
                        name:'Seat Arona',
                        type:'SUV',  
                        price:'68.000', 
                        brand:'Seat', 
                        FuelType:'Gasoline',
                    },
                    { 
                        image: '/src/assets/AutoCar Projcet Asset/imgs/assets/vw-taigo3832-400x300.jpg', 
                        name:'Volswagen Taigo',
                        type:'SUV',  
                        price:'52.000', 
                        brand:'Volswagen', 
                        FuelType:'Eletric',
                    },
                    { 
                        image: '/src/assets/AutoCar Projcet Asset/imgs/assets/2019-vw-t-cross-400x300.jpg', 
                        name:'Volswagen T-Cross',
                        type:'SUV', 
                        price:'47.000', 
                        brand:'Volswagen', 
                        FuelType:'Diesel',
                    },
                    { 
                        image: '/src/assets/AutoCar Projcet Asset/imgs/assets/volkswagen-passat-1280x720-1-400x300.jpg', 
                        name:'Volswagen Passat',
                        type:'Sedan', 
                        price:'32.000', 
                        brand:'Volswagen', 
                        FuelType:'Diesel',
                        
                    },
                ]
            },
        },

        data () {
            return {
                visibleCars: [],
                showAll: false
            }
        },

        // created 
        created() {
            this.visibleCars = this.Card;
        },

        methods: {
            // show all cars button
            showAllCars() {
                this.showAll = true;
                this.visibleCars = [...this.Card, ...this.card2];
            },

            // close all cars button
            closeAllCars() {
                this.showAll = false;
                this.visibleCars = this.Card;
                this.scrollToSection('vehicles');
            },

            // scroll to top of the section
            scrollToSection(id) {
                const section = document.getElementById(id);
                if (section) {
                    const yOffset = -200; // Adjust this value as needed
                    const y = section.getBoundingClientRect().top + window.pageYOffset + yOffset;
                    window.scrollTo({ top: y, behavior: 'smooth' });
                }
            },
        },
    }
</script>

<!-- template -->
<template>

    <!-- card -->
    <div class="card" id="vehicles">
        <div class="card-container">
            <!-- card 1 -->
            <div class="card-container-item" v-for="car in visibleCars" :key="car.name">
                <div class="card-container-item-content">
                    <img :src="car.image" alt="car image">
                    <h1>{{ car.name }} <span class="fa-solid fa-circle-check"></span></h1>
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
    <div class="buttons-container">
      <div class="button-to-see-more-cars" v-if="!showAll">
        <button @click="showAllCars">Show All Cars</button>
      </div>
      <div class="button-to-close-cars" v-else>
        <button @click="closeAllCars">Close</button>
      </div>
    </div>

</template>

<!-- style -->
<style lang="scss" scoped>

@use '../styles/partials/_variables' as *;

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

.buttons-container {
    display: flex;
    justify-content: center;
    align-items: center;
    margin: 2rem;
    
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

    .button-to-close-cars {
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
}

</style>