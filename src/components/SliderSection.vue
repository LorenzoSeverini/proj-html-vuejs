<!-- slider -->
<script>

export default {
    name: 'SliderSection',
    
    props: {
        slider : {
            type: Array,
            default: () => [
                { image: '/src/assets/AutoCar Projcet Asset/imgs/assets/slider-autocar-5.jpg', title: 'Buy And Sell Your Car At Its Value', text:'Find the right price and dealer', a: 'Learn More'},
                { image: '/src/assets/AutoCar Projcet Asset/imgs/assets/slider-autocar-6.jpg', title: 'Buy And Sell Your Car At Its Value', text:'Find the right price and dealer', a: 'Learn More'},
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
    <!-- slider section with props  -->

    <div class="slider-section">
        <div class="slider-section-container">
            <div class="slider-section-container-slider">
                <!-- arrow left and right -->
                <div class="slider-section-container-slider-arrow-left">
                    <i class="fas fa-chevron-left"></i>
                </div>
                <div class="slider-section-container-slider-arrow-right">
                    <i class="fas fa-chevron-right"></i>
                </div>
                <div class="slider-section-container-slider-item" v-for="slide in slider" :key="slide.title">
                    <img :src="slide.image" alt="slider image">
                    <div class="slider-section-container-slider-item-content">
                        <h1>{{ slide.title }}</h1>
                        <p>{{ slide.text }}</p>
                        <a href="#">{{ slide.a }}</a>
                    </div>
                </div>
            </div>
        </div>
    </div>

</template>

<!-- style -->
<style lang="scss" scoped>

@use '../styles/partials/_variables' as *;
@use '../styles/partials/_mixing' as *;

.slider-section {
    width: 100%;
    height: 100vh;
    background-color: $color-primary;
    position: relative;
    overflow: hidden;
    display: flex;
    justify-content: center;
    align-items: center;
    z-index: 1;

    &::before {
        content: '';
        position: absolute;
        width: 100%;
        height: 100%;
        background-color: rgba(0,0,0,0.5);
        z-index: 2;
    }

    &-container {
        width: 100%;
        height: 100%;
        position: relative;
        z-index: 3;
    }

    &-container-slider {
        width: 100%;
        height: 100%;
        position: relative;
        z-index: 3;
    }

    .slider-section-container-slider-arrow-left {
        position: absolute;
        top: 50%;
        left: 0;
        padding-left: 3rem;
        transform: translateY(-50%);
        color: $color-white;
        font-size: 4rem;
        cursor: pointer;
        z-index: 100;

        &:hover {
            color: $color-primary;
        }
    }

    .slider-section-container-slider-arrow-right {
        position: absolute;
        top: 50%;
        right: 0;
        padding-right: 3rem;
        transform: translateY(-50%);
        color: $color-white;
        font-size: 4rem;
        cursor: pointer;
        z-index: 100;

        &:hover {
            color: $color-primary;
        }
    }

    &-container-slider-item {
        width: 100%;
        height: 100%;
        position: relative;
        z-index: 3;

        img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }

        &-content {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            color: $color-white;
            text-align: center;
            z-index: 3;

            h1 {
                font-size: 3rem;
                font-weight: 700;
                margin-bottom: 1rem;
            }

            p {
                font-size: 1.5rem;
                font-weight: 400;
                margin-bottom: 1rem;
            }

            a {
                font-size: 1.5rem;
                font-weight: 400;
                color: $color-white;
                text-decoration: none;
                border: 1px solid $color-white;
                padding: 0.5rem 1rem;
                border-radius: 5px;
                transition: all 0.3s ease-in-out;
                cursor: pointer;

                &:hover {
                    background-color: $color-white;
                   
                }
            }
        }
    }
}

</style>