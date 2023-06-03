<!-- Script -->
<script>
  export default  {
    name: 'AppHeader',
    
    props: {

      links : {
        type: Array,
        default: () => [
          { name: 'Home', link: '#home' },
          { name: 'About Us', link: '#about' },
          { name: 'Vehicles', link: '#vehicles' },
          { name: 'Dealers', link: '#selling' },
          { name: 'Packages', link: '#minicard'},
          { name: 'Blog', link: '#blog'},
          { name: 'Contact', link: '#contact' },
        ],
      },

      image : {
        type: String,
        default: () => '/src/assets/AutoCar Projcet Asset/imgs/assets/logo-autocar11.png' 
      },

      Icon : {
        type: Array,
        default: () => [
          { image: '/src/assets/AutoCar Projcet Asset/padlock.png', text: 'My Account'},
          { image: '/src/assets/AutoCar Projcet Asset/add.png', text: 'Add Car'},
          { image: '/src/assets/AutoCar Projcet Asset/headphones.png', text: '+1(234) 567 89 10'},
        ]
      },
    },

    data() {
      return {
      }
    },

    methods: {
      scrollToSection(sectionId) {
        const section = document.querySelector(sectionId);
        if (section) {
          const yOffset = -200;
          const y = section.getBoundingClientRect().top + window.pageYOffset + yOffset;
          window.scrollTo({ top: y, behavior: 'smooth' });
        }
      },
    },
  }

</script>

<!-- Template -->
<template>
  <div class="nav-bar">
    <div class="nav-bar-logo">
      <img :src="image" alt="logo">
    </div>
    <div class="nav-bar-links">
      <ul>
        <li v-for="link in links" :key="link.name">
          <a @click="scrollToSection(to=link.link)">{{ link.name }}</a>
        </li>
      </ul>
    </div>
    <div class="nav-bar-buttons">
      <ul>
        <li v-for="btn in Icon" :key="btn.text">
          <img :src="btn.image" alt="button">
          <span>{{ btn.text }}</span>
        </li>
      </ul>
    </div>
    <!-- add an hamburger menu -->
    <div class="hamburger">
      <a class="fa-solid fa-bars"></a>
    </div>
  </div>
</template>

<!-- Style -->
<style lang="scss" scoped>

@use '../styles/partials/_variables' as *;
@use '../styles/partials/_mixing' as *;

.nav-bar {
  display: flex;
  justify-content: space-between;
  align-items: center;
  background-color: $color-primary;
  color: $color-secondary;
  font-size: 1.6rem;
  font-weight: 600;
  text-transform: uppercase;
  max-width: 140rem;
  margin: 3.125rem auto;

  .nav-bar-logo {
    width: 20rem;
    display: flex;
    justify-content: center;
    align-items: center;
  }

  .nav-bar-logo img {
    width: 100%;
  }

  .nav-bar-links {
    

    ul {
      display: flex;
      gap: 2rem;
      align-items: center;
      list-style: none;

      li {
        a {
          color: $color-secondary;
          text-decoration: none;
          transition: all 0.3s ease-in-out;
          font-size: 1.3rem;

          &:hover {
            text-decoration: underline;
            cursor: pointer;
          }
        }
      }
    }

    
  }

  .nav-bar-buttons {
    

    ul {
      display: flex;
      gap: 2rem;
      align-items: center;
      list-style: none;

      li {
        display: flex;
        gap: 1rem;
        align-items: center;
        justify-content: center;
        border: 1px solid $color-secondary;
        background-color: $color-secondary;
        padding: 1rem;
        border-radius: 0.5rem;
        transition: all 0.3s ease-in-out;
        cursor: pointer;

        img {
          width: 2rem;
          // change color to white using invert!
          filter: invert(100%);
        }

        span {
          color: $color-primary;
        }
      }
    }
  }

  .hamburger {
    color: $color-secondary;
    font-size: 4rem;
    cursor: pointer;
  }
}
</style>