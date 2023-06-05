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
                    { image: '/src/assets/AutoCar Projcet Asset/imgs/assets/bmw1111.avif', title: 'Buy And Sell Your Car At Its Value', text:'Find the right price and dealer', a: 'Learn More'},
                    { image: '/src/assets/AutoCar Projcet Asset/imgs/assets/ferrari2.avif', title: 'Buy And Sell Your Car At Its Value', text:'Find the right price and dealer', a: 'Learn More'},
                    { image: '/src/assets/AutoCar Projcet Asset/imgs/assets/mercedes.jpeg', title: 'Buy And Sell Your Car At Its Value', text:'Find the right price and dealer', a: 'Learn More'},
                ],
            },
            autoplayInterval: {
                type: Number,
                default: 5000, // 5 seconds
            },
        },

        data () {
            return {
                currentIndex: 0,
                autoplayTimer: null,
            }
        },

        mounted () {
           this.startAutoplay();
        },

        beforeUnmount() {
            this.stopAutoplay();
        },

        computed: {
            currentImage() {
                return this.slider[this.currentIndex]
            },

        },

        methods: {

            previousImage() {
                this.currentIndex = (this.currentIndex - 1 + this.slider.length) % this.slider.length;
                this.restartAutoplay();
            },

            nextImage() {
                this.currentIndex = (this.currentIndex + 1) % this.slider.length;
            },

            startAutoplay() {
                this.autoplayTimer = setInterval(() => {
                    this.nextImage();
                }, this.autoplayInterval);
            }, 
            
            stopAutoplay() {
                clearInterval(this.autoplayTimer);
            },

            restartAutoplay() {
                this.stopAutoplay();
                this.startAutoplay();
            },

            // scroll to the top
            scrollToSection(sectionId) {
                const section = document.querySelector(sectionId);
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
    <!-- slider section with props  -->

    <div class="slider-section" id="home">
        <div class="slider-section-container">
            <div class="slider" id="slider">
                <img :src="currentImage.image" :alt="currentImage.title">
                <button class="previous" @click="previousImage"><a class="fa-solid fa-arrow-left fa-2xl" style="color: #ffffff;"></a></button>
                <button class="next" @click="nextImage"><a class="fa-solid fa-arrow-right fa-2xl" style="color: #ffffff;"></a></button>
            </div>
            <div class="slider-section-container-slider-item-content">
                <h1>{{ currentImage.title }}</h1>
                <p>{{ currentImage.text }}</p>
                <a @click="scrollToSection('#selling')">{{ currentImage.a }}
                    <span class="fa-solid fa-arrow-right"></span>
                </a>
            </div>
        </div>
    </div>

</template>

<!-- style -->
<style lang="scss" scoped>

@use '../styles/partials/_variables' as *;

.slider-section {
    width: 100%;
    height: calc(100vh - 135px);
    background-color: $color-primary;
    position: relative;
    overflow: hidden;
    display: flex;
    justify-content: center;
    align-items: center;
    z-index: 1;

    .slider-section-container {
        width: 100%;
        height: 100%;
        position: relative;
        overflow: hidden;
        display: flex;
        justify-content: center;
        align-items: center;
        z-index: 1;

        .slider {
            width: 100%;
            height: 100%;
            position: relative;
            overflow: hidden;
            display: flex;
            justify-content: center;
            align-items: center;
            z-index: 1;

            img {
                width: 100%;
                height: 100%;
                object-fit: cover;
                position: absolute;
                top: 0;
                left: 0;
                z-index: 1;
                
            }

            .next {
                width: 7rem;
                height: 7rem;
                margin-right: 2.5rem;
                position: absolute;
                background-color: transparent;
                border: none;
                top: 50%;
                right: 0;
                transform: translateY(-50%);
                cursor: pointer;
                transition: all 0.3s ease-in-out;
                z-index: 100;  
            }

            .previous {
                width: 7rem;
                height: 7rem;
                margin-left: 2.5rem;
                background-color: transparent;
                border: none;
                position: absolute;
                top: 50%;
                left: 0;
                transform: translateY(-50%);
                cursor: pointer;
                transition: all 0.3s ease-in-out;
                z-index: 100;   
            }

            .next:hover, .previous:hover {
                background-color: $color-tertiary;
                border-radius: 50%;
                transition: all 0.2s ease-in-out;  
            }
        }

        .slider-section-container-slider-item-content {
            width: 30%;
            position: absolute;
            bottom: 35%;
            left: 5%;
            padding: 2rem;
            color: $color-primary;
            z-index: 100;

            h1 {
                font-size: 5rem;
                font-weight: 700;
                margin-bottom: 1rem;
            }

            p {
                font-size: 2rem;
                margin-bottom: 5rem;
            }

            a {
                font-size: 2rem;
                color: $color-primary;
                text-decoration: none;
                padding-bottom: 0.5rem;
                transition: all 0.3s ease-in-out;
                padding-left: 3rem;


                &:hover {
                    color: $color-primary;
                    text-decoration: underline;
                    cursor: pointer;
                }
            }
        }
    }
}
</style>