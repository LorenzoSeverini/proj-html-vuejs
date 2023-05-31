<!-- Buy or selling? -->
<script>
    export default {
        name: 'SellingBuyCar',

        props: {
            left : {
                type : Array,
                default: () => [
                    { image:'/src/assets/AutoCar Projcet Asset/imgs/assets/aoutcar-about-1.png', },
                ],
            },
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

    <div class="container">
        <div class="container-left">
            <img src="../assets/AutoCar Projcet Asset/imgs/assets/aoutcar-about-1.png" alt="about car">
            <div class="circle-1">24<br> Years of experince</div>
            <div class="circle-2">240<br> special export Team</div>
        </div>
        <div class="container-right">
            <div class="title">Want to Buy or sell a vehicle?</div>
            <div class="subtitle">
                You can put your vehicles for sale by registering on our
                website. Whether you are a dealer or sell personally. Sell your
                vehicle in the most profitable way. With this system. which
                has millions of members. you will be able to buy and sell
                vehicles quickly.
            </div>
            <img src="../assets/AutoCar Projcet Asset/imgs/assets/divider.jpg" alt="divider">
            <div class="container-vehicles">
                <img src="../assets/AutoCar Projcet Asset/imgs/assets/free-fa-brands-400.svg-fonta.svg" alt="">
                <div class="text">
                    <h3>Model vehicles</h3>
                    <p>We are sure that you will find vehicles of suitable models on our website.</p>
                </div>
            </div>
            <div class="container-vehicles">
                <img src="../assets/AutoCar Projcet Asset/imgs/assets/free-fa-v4deprecations.svg-fonta.svg" alt="">
                <div class="text">
                    <h3>2nd Hand Vehicles</h3>
                    <p>You can put your used vehicles for sale by adding them to our website.</p>
                </div>
            </div>
            <div class="button-us">
                <button>Get to know us <span class="fa-solid fa-arrow-right"></span></button>
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
    margin: 10.125rem auto;
    display: flex;

    .container-left {
        width: 50%;
        background-image: url('../assets/AutoCar Projcet Asset/imgs/assets/circle-auto-car-1.png');
        background-repeat: no-repeat;
        text-align: center;
        position: relative;
        margin-right: 6.25rem;

        img {
            object-fit: cover;
            width: 100%;
            object-position: center;
        }

        .circle-1 {
            width: 18rem;
            height: 18rem;
            background-color: $color-secondary;
            border-radius: 50%;
            color: $color-white;
            font-size: 3rem;
            font-weight: 700;
            display: flex;
            justify-content: center;
            align-items: center;
            margin: 2rem auto;
            position: absolute;
            top: 10%;
            left: 10%;
            transform: translate(-5%, -20%);
        }

        .circle-2 {
            width: 18rem;
            height: 18rem;
            background-color: $color-secondary;
            border-radius: 50%;
            color: $color-white;
            font-size: 2.5rem;
            font-weight: 700;
            display: flex;
            justify-content: center;
            align-items: center;
            margin: 2rem auto;
            position: absolute;
            top: 90%;
            right: 2%;
            transform: translate(-3%, -100%);
        }
    }

    .container-right {
        width: 50%;
        padding: 2rem;
        display: flex;
        flex-direction: column;
        

        .title {
            font-size: 3.125rem;
            font-weight: 700;
            color: $color-black;
            margin-bottom: 1.875rem;


        }

        .subtitle {
            font-size: 1.875rem;
            font-weight: 400;
            color: $color-black;
            margin-bottom: 1.875rem;
        }

        img {
            width: 20%;
            margin-bottom: 1.875rem;
        }

        .container-vehicles {
            display: flex;
            height: 10rem;

            img {
                width: 10%;
                height: 30%;
                margin-right: 1.875rem;
                fill: rgb(184, 167, 167);
                color: rgb(204, 75, 75);
                background-color: black;
                display: flex;
                justify-content: center;
                align-items: center;
            }

            .text {

                h3 {
                    font-size: 1.875rem;
                    font-weight: 700;
                    color: $color-black;
                    margin-bottom: 1.875rem;
                }

                p {
                    font-size: 1.5rem;
                    font-weight: 400;
                    color: $color-black;
                    margin-bottom: 1.875rem;
                }
            }
            
        }

        .button-us {
            display: flex;
            margin-bottom: 1.875rem;
            

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
}
</style>