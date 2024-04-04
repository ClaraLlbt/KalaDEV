<script>
export default {
  name: 'Navbar',
  data() {
    return {
      mobileFormat: false
    }
  },
  mounted() {
    const el = document.querySelector('.banner-ctr')
    const navBlur = document.querySelector('.navbar .nav')
    document.addEventListener('scroll', () => {
      const { scrollTop, scrollHeight, clientHeight } = document.documentElement
      const topElementToTopViewport = el.getBoundingClientRect().top

      if (scrollTop > (scrollTop + topElementToTopViewport).toFixed() - clientHeight * 0.1) {
        navBlur.classList.add('blur')
      }
    })
    this.navHidden()
    if (window.matchMedia('(max-width: 768px)').matches) {
      /* La largeur minimum de l'affichage est 600 px inclus */
      this.mobileFormat = true
      this.navHidden()
    }
  },
  methods: {
    navHidden() {
      const el = document.querySelector('.contact')
      const mobileNav = document.getElementsByClassName('navbar-mobile')
      document.addEventListener('scroll', () => {
        const { scrollTop, scrollHeight, clientHeight } = document.documentElement
        const topElementToTopViewport = el.getBoundingClientRect(scrollHeight).top

        if (scrollTop > (scrollTop + topElementToTopViewport).toFixed() - clientHeight * 0.1) {
          mobileNav[0].classList.add('hiden')
        }
        if (scrollTop > (scrollTop - topElementToTopViewport).toFixed() - clientHeight * 0.1) {
          mobileNav[0].classList.remove('hiden')
        }
      })
    }
  }
}
</script>

<template>
  <!-- IF MOBILE FORMAT IS NOT DETECTED, SHOW THIS NAV -->
  <div v-if="mobileFormat == false" class="container-fluid navbar">
    <a class="navbar-brand" href="#">
      <img src="../assets/kaladev-logo.svg" width="150" height="150" alt="" />
    </a>
    <ul class="nav justify-content-center">
      <li class="nav-item btn-effect">
        <a class="nav-link" aria-current="page" href="#">HOME</a>
      </li>
      <li class="nav-item btn-group btn-effect" role="group">
        <button
          type="button"
          class="btn dropdown-toggle"
          data-bs-toggle="dropdown"
          aria-expanded="false"
        >
          SERVICES
        </button>
        <ul class="dropdown-menu">
          <li><a class="dropdown-item" href="#turnkey-ctr">Solution "Clé en main"</a></li>
          <li><a class="dropdown-item" href="#bespoke-ctr">Solution Sur-mesure</a></li>
        </ul>
      </li>
      <li class="nav-item btn-effect">
        <a class="nav-link" href="#contact">CONTACT</a>
      </li>
    </ul>
  </div>

  <!-- IF MOBILE FORMAT IS DETECTED, SHOW THIS MOBILE NAV -->
  <div
    id="navbar-mobile"
    v-else-if="mobileFormat == true"
    class="container-fluid navbar navbar-mobile"
  >
    <ul class="nav justify-content-center">
      <li class="nav-item mobile-item">
        <a class="nav-link active" aria-current="page" href="#"
          ><i class="bi bi-house-door-fill"></i
        ></a>
      </li>
      <li class="nav-item mobile-item">
        <a class="nav-link" href="#aboutthebee"><i class="bi bi-gear"></i></a>
      </li>

      <li class="nav-item mobile-item">
        <a class="nav-link" href="#work"><i class="bi bi-code-slash"></i></a>
      </li>
      <li class="nav-item mobile-item">
        <a class="nav-link" href="#contact"><i class="bi bi-envelope-at-fill"></i></a>
      </li>
    </ul>
  </div>
</template>

<style lang="scss">
.navbar {
  transform: translateY(-195px);
  animation: deployeNav 1s 0.5s forwards;
  position: fixed;
  z-index: 1;
  .navbar-brand {
    position: fixed;
    top: 0;
    left: 0;
  }
  .nav {
    font-size: x-large;
    margin: auto;
    .nav-item {
      margin: 0.5em 1em;
      .btn.dropdown-toggle {
        font-size: x-large;
        &:focus,
        &:active {
          border: none;
          box-shadow: none;
        }
      }
      .btn-check:checked + .btn,
      .btn.active,
      .btn.show,
      .btn:first-child:active,
      :not(.btn-check) + .btn:active {
        border: none;
      }
      ul.dropdown-menu {
        background: none;
        backdrop-filter: blur(100px);
        border-radius: 0;
        border: 0;
        top: 66px;
      }
      a.dropdown-item.active,
      a.dropdown-item:active {
        background-color: #f2f3f5;
      }
    }
  }
  .nav.blur::before {
    content: '';
    width: 800px;
    height: 85%;
    position: absolute;
    backdrop-filter: blur(101px);
    border-radius: 10px;
  }
}

/* Navbar Animations*/
.nav * {
  box-sizing: border-box;
  transition: all 0.35s ease;
}
.nav li,
button {
  color: black;
  position: relative;
  text-decoration: none;
}
.nav li a {
  color: black;
}
.nav li a:hover {
  color: black;
}
.btn-effect::before,
.btn-effect::after {
  content: '';
  height: 14px;
  width: 14px;
  position: absolute;
  transition: all 0.35s ease;
  opacity: 0;
}
.btn-effect::before {
  content: '';
  right: 0;
  top: 0;
  border-top: 2px solid black;
  border-right: 2px solid black;
  transform: translate(-100%, 50%);
}
.btn-effect::after {
  content: '';
  left: 0;
  bottom: 0;
  border-bottom: 2px solid black;
  border-left: 2px solid black;
  transform: translate(100%, -50%);
}

.nav li:hover:before,
.nav li:hover:after,
.btn-effect:hover::before,
.btn-effect:hover::after {
  transform: translate(0, 0);
  opacity: 1;
}
@media screen and (max-width: 767px) {
  .navbar-mobile {
    position: fixed;
    bottom: 15px;
    z-index: 1;
    transform: translateY(100px);
    animation: deployeMobileNav 1.5s 1s forwards;
    box-shadow: inset -1px -4px 20px lightgray;
    background: white;
    width: 70%;
    left: 0;
    right: 0;
    border-radius: 15px;
    .nav {
      width: 100%;
      .nav-item.mobile-item {
        margin: auto;
        a {
          padding: 0;
          // i{
          //   color: grey;
          //   &::before{
          //   background: none;
          //   -webkit-text-fill-color: initial;
          // }}
        }
      }
      // .item-dark .btn i::before{
      //   background: none;
      //   -webkit-text-fill-color: initial;
      //   color: grey;
      // }
    }
    .nav .nav-item.mobile-item::after,
    .nav .nav-item.mobile-item::before {
      content: none;
    }
  }
  .navbar-mobile .navbar-mobile.hiden {
    transform: translateY(0);
    animation: hideMobileNav 1.5s 1s forwards;
  }
  @keyframes deployeMobileNav {
    0% {
      transform: translateY(100px);
    }
    100% {
      transform: translateY(0);
    }
  }
}
//ANIMATIONS KEYFRAMES

@keyframes deployeNav {
  0% {
    transform: translateY(-195px);
  }
  100% {
    transform: translateY(0);
  }
}

@keyframes hideMobileNav {
  0% {
    transform: translateY(0);
  }
  100% {
    transform: translateY(100px);
  }
}
</style>