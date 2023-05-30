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
                    }
                ],
            },
        }
    }

</script>

<!-- template -->
<template>

    <div class="container">
        <div class="Customer-title">
            <div class="title">What Our Customers Saying?</div>
            <div class="subtitle">Opinions from our happy customers.</div>
        </div>
        <div class="container-card">
            <div class="customer">
                <div class="customer-card" v-for="item in customer" :key="item.id">
                    <div class="customer-card-text">{{ item.text }}</div>
                    <div class="customer-card-image">
                        <img :src="item.image" alt="customer">
                    </div>
                    <div class="customer-card-name">{{ item.name }}</div>
                </div>
            </div>
        </div> 
    </div>

</template>

<!-- style -->
<style lang="scss" scoped>

@use '../styles/partials/_variables' as *;
@use '../styles/partials/_mixing' as *;

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
        padding: 5rem;

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

        .customer {
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

                // hover

                &:hover {
                    box-shadow: 0 0 1rem rgba(0, 0, 0, 0.2);
                    transition: all 0.3s ease-in-out;
                    transform: scale(1.05);
                    cursor: pointer;
                }

                .customer-card-text {
                    font-size: 1.5rem;
                    font-weight: 400;
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
    }
}

</style>