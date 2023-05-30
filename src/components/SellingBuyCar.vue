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
            <img :src="left.image" alt="about car">
            
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
            <div class="button-us">
                <button>Show All Cars</button>
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
    display: flex;
    min-height: 1000px;

    .container-left {
        width: 50%;
        background-image: url('../assets/AutoCar Projcet Asset/imgs/assets/circle-auto-car-1.png');
        background-repeat: no-repeat;
        text-align: center;

        img {
            width: 100%;
            height: 100%;
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