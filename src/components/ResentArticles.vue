<!-- resent articles -->

<script>
    export default {
        name: 'ResentArticles',

        props: {
            articles: {
                type: Array,
                default: () => [
                    {
                        image: '/src/assets/AutoCar Projcet Asset/imgs/assets/news-autocar-1-300x180.jpg',
                        date: '12.05.2021',
                        title: 'Why is BMW loved?',
                        text: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed ut purus eget nunc ut dignissim cursus. Sed mollis, nisl quis ornare molestie, diam magna.',
                    },
                    {
                        image: '/src/assets/AutoCar Projcet Asset/imgs/assets/news-autocar-2-300x180.jpg',
                        date: '12.05.2021',
                        title: 'How solid is Audi?',
                        text: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed ut purus eget nunc ut dignissim cursus. Sed mollis, nisl quis ornare molestie, diam magna.',
                    },
                    {
                        image: '/src/assets/AutoCar Projcet Asset/imgs/assets/news-autocar-6-300x180.jpg',
                        date: '12.05.2021',
                        title: 'What brand is Skoda?',
                        text: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed ut purus eget nunc ut dignissim cursus. Sed mollis, nisl quis ornare molestie, diam magna.', 
                    },
                    {
                        image: '/src/assets/AutoCar Projcet Asset/imgs/assets/news-autocar-5-300x180.jpg',
                        date: '12.05.2021',
                        title: 'Is the Auris diesel?',
                        text: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed ut purus eget nunc ut dignissim cursus. Sed mollis, nisl quis ornare molestie, diam magna.', 
                    },
                ],
            },
        },
    }

</script>

<!-- template -->
<template>

    <div class="container">
        <div class="titles">
            <div class="title">Resent Articles</div>
            <div class="subtitle">Useful information about car.</div>
        </div>
        <div class="container-articles-card">
            <div class="articles-card" v-for="item in articles" :key="item.id">
                <div class="articles-card-image">
                    <img :src="item.image" alt="articles">
                </div>
                <div class="articles-card-date">{{ item.date }}</div>
                <div class="articles-card-title">{{ item.title }}</div>
                <div class="articles-card-text">{{ item.text }}</div>
                <div class="button-more">
                    <button>Show more</button>
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
    max-width: 140rem;
    margin: 3.125rem auto;
    display: flex;
    flex-direction: column;

    .titles {
        text-align: center;
        display: flex;
        flex-direction: column;
        align-items: center;
        gap: 2rem;
        padding: 5rem;

        .title {
            font-size: 3.125rem;
            font-weight: 700;
            color: $color-secondary;
        }

        .subtitle {
            font-size: 1.875rem;
            font-weight: 400;
            color: $color-secondary;
        }
    }

    .container-articles-card {
        display: flex;
        justify-content: center;
        align-items: center;
        gap: 2rem;
        padding: 5rem;
        max-width: 140rem;
        margin: 3.125rem auto;

        .articles-card {
            width: 25%;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            gap: 2rem;
            padding: 2rem;
            border: 1px solid $color-tertiary;
            border-radius: 1rem;
            transition: all 0.3s ease-in-out;
            box-shadow: 0 0.5rem 1rem rgba($color-tertiary, 0.2);

            &:hover {
                transform: translateY(-0.5rem);
                box-shadow: 0 1rem 2rem rgba($color-tertiary, 0.2);
                cursor: pointer;
            }

            .articles-card-image {
                width: 100%;
                height: 15rem;
                overflow: hidden;

                img {
                    width: 100%;
                    height: 100%;
                    object-fit: cover;
                }
            }

            .articles-card-date {
                font-size: 1.25rem;
                font-weight: 400;
                color: $color-tertiary;
            }

            .articles-card-title {
                font-size: 1.875rem;
                font-weight: 700;
                color: $color-secondary;
            }

            .articles-card-text {
                font-size: 1.25rem;
                font-weight: 400;
                color: $color-tertiary;
            }

            .button-more {
            display: flex;
            margin-bottom: 1.875rem;
            

                button {
                    padding: 2rem 2rem;
                    border: none;
                    background-color: $color-secondary;
                    color: $color-primary;
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
}
</style>