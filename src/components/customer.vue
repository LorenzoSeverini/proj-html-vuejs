<script>

    export default {
        name: 'customer',

        props: {
            customer: {                
                type: Array,
                default: () => [
                    { 
                        text:'We are a gallery vehicle dealer. Before we met this site. our sales were sluggish.', 
                        image:'/src/assets/AutoCar Projcet Asset/imgs/assets/man1.png', 
                        name:'Adam',
                    },
                    {
                        text:'One of the quality websites I apply to rent a car. There are hundreds of different tools.',
                        image:'/src/assets/AutoCar Projcet Asset/imgs/assets/man2.png',
                        name:'Emma',
                    },
                    {
                        text:'I was trying to sell my car. And I put it here and sold it for more than it was worth.',
                        image:'/src/assets/AutoCar Projcet Asset/imgs/assets/testimonial2-1.png',
                        name:'John',
                    },
                    {
                        text:'A fast and reliable vehicle selling site. Rare quality website with hundreds of model vehicles.',
                        image:'/src/assets/AutoCar Projcet Asset/imgs/assets/testimonial4-1.png',
                        name:'John',   
                    },  
                ],
            },

            customer2: {
                type: Array,
                default: () => [
                    { 
                        text:'We are a gallery vehicle dealer. Before we met this site. our sales were sluggish.', 
                        image:'/src/assets/AutoCar Projcet Asset/imgs/assets/man1.png', 
                        name:'Adam',
                    },
                    {
                        text:'One of the quality websites I apply to rent a car. There are hundreds of different tools.',
                        image:'/src/assets/AutoCar Projcet Asset/imgs/assets/man2.png',
                        name:'Emma',
                    },
                    {
                        text:'I was trying to sell my car. And I put it here and sold it for more than it was worth.',
                        image:'/src/assets/AutoCar Projcet Asset/imgs/assets/testimonial2-1.png',
                        name:'John',
                    },
                    {
                        text:'A fast and reliable vehicle selling site. Rare quality website with hundreds of model vehicles.',
                        image:'/src/assets/AutoCar Projcet Asset/imgs/assets/testimonial4-1.png',
                        name:'John',   
                    },  
                ]
            },
        },

        data() {
            return {
                showFirstArray: true,
            };
        },


        created() {
            setInterval(() => {
            this.showFirstArray = !this.showFirstArray;
            }, 5000);
        },
    }
</script>

<!-- template -->
<template>

    <div class="container" id="about">
        <div class="Customer-title">
            <div class="title-icon">
                <a class="fa-regular fa-thumbs-up fa-2xl" style="color: #f4f6fb;"></a>
                <div>
                    <span class="fa-regular fa-star fa-sm" style="color: #9e9e9e;"></span>
                    <span class="fa-regular fa-star fa-sm" style="color: #9e9e9e;"></span>
                    <span class="fa-regular fa-star fa-sm" style="color: #9e9e9e;"></span>
                </div>
            </div>
            <div class="title">What Our Customers Saying?</div>
            <div class="subtitle">Opinions from our happy customers.</div>
        </div>

        <div class="container-card">
            <!-- 1 -->
            <div class="customer" v-show="showFirstArray">
                <div class="customer-card" v-for="item in customer" :key="item.id">
                    <div class="customer-card-text">{{ item.text }}</div>
                    <div class="customer-card-image">
                        <img :src="item.image" alt="customer">
                    </div>
                    <div class="customer-card-name">{{ item.name }}</div>
                </div>
            </div>
            <!-- 2 -->
            <div class="customer2" v-show="!showFirstArray">
                <div class="customer-card" v-for="item in customer2" :key="item.id">
                    <div class="customer-card-text">{{ item.text }}</div>
                    <div class="customer-card-image">
                        <img :src="item.image" alt="customer">
                    </div>
                    <div class="customer-card-name">{{ item.name }}</div>
                </div>
            </div>
        </div>

        <!-- Buttons -->
        <div class="slide-buttons-cont">
            <!-- first -->
            <button @click="showFirstArray = true" class="slide-button1"></button>
            <!-- second -->
            <button @click="showFirstArray = false" class="slide-button2"></button>
        </div>
    </div>

</template>

<!-- style -->
<style lang="scss" scoped>

@use '../styles/partials/_variables' as *;

.container {
    background-image: url('../assets/AutoCar Projcet Asset/imgs/assets/comment-bg-autocar.jpg');
    background-repeat: no-repeat;
    background-size: cover;
    background-position: center;
    padding: 6rem;

    .Customer-title {
        text-align: center;
        display: flex;
        flex-direction: column;
        align-items: center;
        gap: 2rem;
        
        .title-icon {
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
        }

        .title {
            font-size: 3.125rem;
            font-weight: 700;
            color: $color-white;
        }

        .subtitle {
            font-size: 1.875rem;
            font-weight: 400;
            color: $color-white;
        }
    }

    .container-card {
        display: flex;
        justify-content: center;
        align-items: center;
        gap: 2rem;
        padding: 5rem;
        max-width: 140rem;
        margin: 3.125rem auto;

        .customer, .customer2 {
            display: flex;
            justify-content: center;
            align-items: center;
            gap: 2rem;

            .customer-card {
                width: 25%;
                height: 35rem;
                background-color: $color-white;
                border-radius: 1.25rem;
                padding: 2rem;
                display: flex;
                flex-direction: column;
                justify-content: center;
                align-items: center;
                gap: 2rem;

                &:hover {
                    box-shadow: 0 0 1rem rgba(0, 0, 0, 0.2);
                    transition: all 0.3s ease-in-out;
                    transform: scale(1.05);
                    cursor: pointer;
                }

                .customer-card-text {
                    font-size: 1.5rem;
                    font-weight: 700;
                    color: $color-black;
                    text-align: center;
                }

                .customer-card-image {
                    width: 10rem;
                    height: 10rem;
                    border-radius: 50%;
                    overflow: hidden;

                    img {
                        width: 100%;
                        height: 100%;
                    }
                }

                .customer-card-name {
                    font-size: 1.5rem;
                    font-weight: 700;
                    color: $color-black;
                }
            }
        }

        .customer2 .customer-card {
            background-color: $color-secondary;
        }

    }

    .slide-buttons-cont {
        display: flex;
        justify-content: center;
        align-items: center;
        gap: 2rem;
        
        .slide-button1 {
            width: 10rem;
            height: 1.5rem;
            background-color: $color-primary;
            border: 1px solid $color-black;
            border-radius: .625rem;
            transition: background-color 3s ease-in-out;
            cursor: pointer;

            &:hover {
                background-color: $color-secondary;
                transition: background-color 0.3s ease-in-out;
            }
        }

        .slide-button2 {
            width: 5rem;
            height: 1.5rem;
            background-color: $color-secondary;
            border: 1px solid $color-black;
            border-radius: .625rem;
            transition: background-color 3s ease-in-out;
            cursor: pointer;

            &:hover {
                background-color: $color-primary;
                transition: background-color 0.3s ease-in-out;
            }
        }
    }
}

</style>