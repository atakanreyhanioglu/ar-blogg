<template>
  <header>
    <nav class="nav-container">
      <div class="branding">
        <NuxtLink class="header" to="/">ARBlogs</NuxtLink>
      </div>
      <div class="nav-links">
        <ul v-show="!mobileNav">
          <NuxtLink class="link" to="#">Home</NuxtLink>
          <NuxtLink class="link" to="#">Blogs</NuxtLink>
          <NuxtLink class="link" to="#">Create Post</NuxtLink>
          <NuxtLink class="link" to="#">Login/Register</NuxtLink>
        </ul>
      </div>
    </nav>
    <menuIcon class="menu-icon" @click="toggleMobileNav" v-show="mobile"/>
    <transition class="mobile-nav">
      <ul class="mobile" v-show="mobileNav">
        <NuxtLink class="link" to="#">Home</NuxtLink>
        <NuxtLink class="link" to="#">Blogs</NuxtLink>
        <NuxtLink class="link" to="#">Create Post</NuxtLink>
        <NuxtLink class="link" to="#">Login/Register</NuxtLink>
      </ul>
    </transition>
  </header>
</template>
<script>
import menuIcon from '../assets/icons/bars.svg'
export default {
  name: 'NavigationComponent',
  components: {
    menuIcon
  },
  mounted() {
    window.addEventListener('resize', this.checkScreen);
    this.checkScreen()
  },
  data() {
    return {
      mobile: null,
      mobileNav: null,
      windowWidth: null
    }
  },
  methods: {
    checkScreen() {
      this.windowWidth = window.innerWidth;
      if (this.windowWidth <= 750) {
        this.mobile = true;
        return
      }
      this.mobile = false
      this.mobileNav = false
    },
    toggleMobileNav() {
      this.mobileNav = !this.mobileNav
    }
  }
}
</script>
<style>
  header {
    background-color: #ffffff;
    padding: 0 25px;
    box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1), 0 2px 4px -1px rgba(0, 0, 0, 0.06);
    z-index: 99;
  }
  .link {
    font-weight: 500;
    padding: 0 8px;
    transition: .3s color ease;
  }
  .link:hover{
    color: #069A8E;
  }
  nav {
    display: flex;
    padding: 25px 0;
  }
  .branding {
    display: flex;
    align-items: center;
  }
  .header {
    font-weight: 600;
    font-size: 24px;
    color: black;
    text-decoration: none;
  }
  .nav-links {
    position: relative;
    display: flex;
    align-items: center;
    justify-content: flex-end;
    flex: 1;
  }
  ul {
    margin-right: 32px;
    margin-bottom: 5px;
  }
  .link {
    margin-right: 32px;
  }
  .link:last-child {
    margin-right: 0;
  }


.menu-icon {
  cursor: pointer;
  position: absolute;
  top: 28px;
  right: 20px;
  height: 25px;
  width: auto;
}

@media screen and (max-width: 750px) {
  .mobile-nav, .mobile {
    padding: 20px;
    width: 70%;
    max-width: 250px;
    display: flex;
    flex-direction: column;
    position: fixed;
    height: 100%;
    top: 0;
    left: 0;
    background-color: whitesmoke;
    -webkit-animation: scale-up-hor-left 0.4s cubic-bezier(0.390, 0.575, 0.565, 1.000) both;
    animation: scale-up-hor-left 0.4s cubic-bezier(0.390, 0.575, 0.565, 1.000) both;
  }

  @-webkit-keyframes scale-up-hor-left {
    0% {
      -webkit-transform: scaleX(.4);
      transform: scaleX(.4);
      -webkit-transform-origin: 0 0;
      transform-origin: 0 0
    }
    100% {
      -webkit-transform: scaleX(1);
      transform: scaleX(1);
      -webkit-transform-origin: 0 0;
      transform-origin: 0 0
    }
  }@keyframes scale-up-hor-left {
     0% {
       -webkit-transform: scaleX(.4);
       transform: scaleX(.4);
       -webkit-transform-origin: 0 0;
       transform-origin: 0 0
     }
     100% {
       -webkit-transform: scaleX(1);
       transform: scaleX(1);
       -webkit-transform-origin: 0 0;
       transform-origin: 0 0
     }
   }
  .nav-links {
    display: none;
  }

  .link {
    padding: 15px 0;
    color: black;
  }
}
</style>
