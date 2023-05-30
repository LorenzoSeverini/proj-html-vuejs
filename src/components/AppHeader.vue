<!-- Script -->
<script>

  export default  {
    name: 'AppHeader',
    
    props: {
      // props with nav link and logo image path, title 

      links : {
        type: Array,
        default: () => [
          { name: 'Home', link: '/' },
          { name: 'About Us', link: '/about' },
          { name: 'Vehicles', link: '/contact' },
          { name: 'Dealers', link: '/contact' },
          { name: 'Packages', link: '/contact'},
          { name: 'Blog', link: '/contact'},
          { name: 'Contact', link: '/contact' },
        ],
      },

      image : {
        type: String,
        default: () => '/src/assets/AutoCar Projcet Asset/imgs/assets/logo-autocar11.png'
      },

      button : {
        type: String,
        default: () => [
          { image: '/src/assets/AutoCar Projcet Asset/padlock.png', text: 'My Account'},
          { image: '/src/assets/AutoCar Projcet Asset/add.png', text: 'Add Car'},
          { image: '/src/assets/AutoCar Projcet Asset/headphones.png', text: '+1(234) 567 89 10'},
        ]
      },
    },

    data() {
      return {
        // 
      }
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
          <a :to="link.link">{{ link.name }}</a>
        </li>
      </ul>
    </div>
    <div class="nav-bar-buttons">
      <ul>
        <li v-for="btn in button" :key="btn.text">
          <img :src="btn.image" alt="button">
          <span>{{ btn.text }}</span>
        </li>
      </ul>
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
  height:150px;
  background-color: $color-primary;
  color: $color-black;
  font-size: 1.6rem;
  font-weight: 600;
  text-transform: uppercase;
  margin : 0 12.5rem;

  .nav-bar-logo {
    width: 20rem;
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
          color: $color-black;
          text-decoration: none;
          transition: all 0.3s ease-in-out;

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

        img {
          width: 2rem;
        }
      }
    }
  }


}
</style>
