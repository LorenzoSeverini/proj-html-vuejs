<!-- footer -->

<script>
import { ref, onMounted, onBeforeUnmount } from 'vue';

    export default {
        name: 'footerino',

        props: {

            logofooter: {
                type: String,
                default: '/src/assets/AutoCar Projcet Asset/imgs/assets/logo-footer-autocar11.png',
            },
           
            account : {
                type: Array,
                default : () => [
                    {
                        title: 'Account',
                        links: [
                            {
                                name: 'My Account',
                                url: '#'
                            },
                            {
                                name: 'Cart',
                                url: '#'
                            },
                            {
                                name: 'Packages',
                                url: '#'
                            },
                            {
                                name: 'Wishlist',
                                url: '#'
                            },
                            {
                                name: 'Checkout',
                                url: '#'
                            },
                        ]
                    }
                ]
            },  

            information : {
                type: Array,
                default : () => [ 
                    {
                        title: 'Quick Links',
                        links: [
                            {
                                name: 'About Us',
                                url: '#'
                            },
                            {
                                name: 'Delivery Information',
                                url: '#'
                            },
                            {
                                name: 'Privacy Policy',
                                url: '#'
                            },
                            {
                                name: 'Terms & Conditions',
                                url: '#'
                            },
                            {
                                name: 'Contact',
                                url: '#'
                            },
                        ]
                    }, 
                ]     
            },
        },

        setup() {
            const showScrollToTop = ref(false);

            const handleScroll = () => {
                showScrollToTop.value = window.scrollY > window.innerHeight;
            };

            const scrollToTop = () => {
                window.scrollTo({ top: 0, behavior: 'smooth' });
            };

            onMounted(() => {
                window.addEventListener('scroll', handleScroll);
            });

            onBeforeUnmount(() => {
                window.removeEventListener('scroll', handleScroll);
            });


            return {
                showScrollToTop,
                scrollToTop,
            };
        },
    }
</script>

<!-- template -->
<template>
    <div class="container" id="contact">
        <!-- first -->
        <div class="col">
            <div class="first">
                <img :src="logofooter" alt="logo">
                <div class="icon">
                    <a class="fa-solid fa-location-dot"></a>
                    <span>New Jersey. USA</span>
                </div>
                <div class="icon">
                    <a class="fa-solid fa-phone-volume"></a>
                    <span>+1 (234) 567 8910</span>
                </div>
                <div class="icon">
                    <a class="fa-solid fa-regular fa-envelope"></a>
                    <span>example@example.com</span>
                </div>
                <div class="social">
                    <a class="fa-brands fa-facebook-f"></a>
                    <a class="fa-brands fa-twitter"></a>
                    <a class="fa-brands fa-instagram"></a>
                </div>
            </div>
        </div>
        <!-- second -->
        <div class="col">
            <div class="second">
                <h3>Join Our Newsletter</h3>
                <p>Subscribe to be informed about our services and products.</p>
                <div class="input-group">
                <input type="text" class="form-control" placeholder="Enter your email address" aria-label="Recipient's username">
                <button class="btn-subscribe" type="button" id="button-addon2">Subscribe</button>
            </div>
            </div>
        </div>
        <!-- third -->
        <div class="col">
            <div class="third">
                <h3>My Account</h3>
                <ul>
                    <li v-for="item in account" :key="item.title">
                        <a href="#" v-for="link in item.links" :key="link.name">{{ link.name }}</a>
                    </li>
                </ul>
            </div>
        </div>
        <!-- four -->
        <div class="col">
            <div class="fourth">
                <h3>Quick Links</h3>
                <ul>
                    <li v-for="item in information" :key="item.title">
                        <a href="#" v-for="link in item.links" :key="link.name">{{ link.name }}</a>
                    </li>
                </ul>
            </div>
        </div>
    </div>

    <!-- button to scroll to the top of the page  -->
    <button v-show="showScrollToTop" @click="scrollToTop" class="scroll-to-top">
        <span class="fa-solid fa-arrow-up"></span>
    </button>
    <!-- copyright -->
    <div class="copyright">@ 2022 Autocar - All Rights Reserved.</div>
</template>

<!-- style -->
<style lang="scss" scoped>

@use '../styles/partials/_variables' as *;

.container {
    max-width: 140rem;
    margin: 3.125rem auto;
    display: flex;
    gap: 2rem;
    padding: 1rem;
   

    .col {
        width: calc(25% - 2rem);
        display: flex;
        flex-direction: column;
        gap: 2rem;
        padding: 2rem;
        color: $color-primary;

        img {
            width: 100%;
        }
    }

    .first {
        display: flex;
        flex-direction: column;
        gap: 2rem;

        .icon {
            display: flex;
            gap: 1rem;
            align-items: center;

            a {
                font-size: 1.5rem;
                font-weight: 400;
                color: $color-primary;
                cursor: pointer;
            }

            span {
                font-size: 1.5rem;
                font-weight: 400;
                color: $color-primary;
            }
        }

        .social {
            display: flex;
            gap: 2rem;

            a {
                font-size: 1.5rem;
                font-weight: 400;
                color: $color-primary;
                cursor: pointer;
            }

            &:hover {
                cursor: pointer;
            }
        }
    }

    .second {
        display: flex;
        flex-direction: column;
        gap: 2rem;

        h3 {
            font-size: 2rem;
            font-weight: 700;
            color: $color-primary;
        }

        p {
            font-size: 1.4rem;
            font-weight: 400;
            color: $color-primary;
        }

        .input-group {
            width: 100%;
            display: flex;
            flex-direction: column;
            gap: 1rem;

            input {
                width: 100%;
                height: 3.5rem;
                border: 1px solid $color-primary;
                border-radius: 0.5rem;
                padding: 0 1rem;
                font-size: 1.125rem;
                font-weight: 400;
                color: $color-secondary;
            }

            .btn-subscribe {
                width: 100%;
                height: 3.5rem;
                border: 1px solid $color-primary;
                border-radius: 0.5rem;
                background-color: $color-primary;
                color: $color-secondary;
                font-size: 1.125rem;
                font-weight: 400;
                cursor: pointer;

                &:hover {
                    background-color: $color-tertiary;
                    color: $color-primary;
                }
            }
        }
    }

    .third {
        display: flex;
        flex-direction: column;
        gap: 2rem;

        h3 {
            font-size: 2rem;
            font-weight: 700;
            color: $color-primary;
        }

        ul {
            display: flex;
            flex-direction: column;
            justify-content: flex-start;
            gap: 1rem;

            li {
                display: flex;
                flex-direction: column;
                gap: 1rem;

                a {
                    font-size: 1.5rem;
                    font-weight: 400;
                    color: $color-primary;
                    text-decoration: none;
                    cursor: pointer;

                    &:hover {
                        text-decoration: underline;
                    }
                }
            }
        }
    }

    .fourth {
        display: flex;
        flex-direction: column;
        gap: 2rem;

        h3 {
            font-size: 2rem;
            font-weight: 700;
            color: $color-primary;
        }

        ul {
            display: flex;
            flex-direction: column;
            gap: 1rem;

            li {
                display: flex;
                flex-direction: column;
                gap: 1rem;

                a {
                    font-size: 1.5rem;
                    font-weight: 400;
                    color: $color-primary;
                    text-decoration: none;
                    cursor: pointer;

                    &:hover {
                        text-decoration: underline;
                    }
                }
            }
        }
    }
}

.scroll-to-top {
    position: fixed;
    bottom: 2rem;
    right: 2rem;
    width: 4rem;
    height: 4rem;
    border-radius: 50%;
    background-color: $color-primary;
    color: $color-secondary;
    font-size: 2rem;
    font-weight: 400;
    display: flex;
    justify-content: center;
    align-items: center;
    cursor: pointer;
    z-index: 2;
    border: rgb(161, 43, 43) 2px solid;

    &:hover {
        background-color: $color-tertiary;
        transition: all 0.3s ease-in-out;
    }
}

.copyright {
    width: 100%;
    padding-bottom: 3rem;
    height: 3.5rem;
    background-color: $color-secondary;
    color: $color-primary;
    font-size: 1.125rem;
    font-weight: 400;
    display: flex;
    justify-content: center;
    align-items: center;
}

</style>