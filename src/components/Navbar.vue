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
    if (window.matchMedia('(max-width: 768px)').matches) {
      /* La largeur minimum de l'affichage est 600 px inclus */
      this.mobileFormat = true
    }
  }
}
</script>

<template>
  <!-- IF MOBILE FORMAT IS NOT DETECTED, SHOW THIS NAV -->
  <div v-if="mobileFormat == false" class="container-fluid navbar">
    <a class="navbar-brand" href="#">
      <img src="../assets/kaladev-logo.svg" width="120" height="120" alt="" />
    </a>
    <ul class="nav justify-content-center">
      <li class="nav-item btn-effect">
        <a class="nav-link" aria-current="page" href="#">HOME</a>
      </li>
      <li class="nav-item btn-effect">
        <a class="nav-link" aria-current="page" href="#about">À PROPOS</a>
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
  <div id="navbar-mobile" v-else-if="mobileFormat == true" class="container-fluid navbar">
    <button
      class="btn btn-offcanvas"
      type="button"
      data-bs-toggle="offcanvas"
      data-bs-target="#offcanvasRight"
      aria-controls="offcanvasRight"
    >
      <img
        src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAACYAAAAmCAYAAACoPemuAAAACXBIWXMAAAsTAAALEwEAmpwYAAAAl0lEQVR4nO3UMQ6CQBCF4b+hMFTcQ0tbKm/BFTDacQctqbyQUhhv4FVYYzItJsDMNr4v+dudVy2IiLgogSqocumoFhiBFNRoN2a7Bo5K1mXJsAKogUNQtd0QEfHUAAPwzNxgtyc9Mvz2aaL7r2F7oAdumevttohIlA1wBLqVtfaWm7PjD3/yHLYDXsB7Zd83tp7DROTvfQBRgq7kD3VlFgAAAABJRU5ErkJggg=="
      />
    </button>

    <div
      class="offcanvas offcanvas-end"
      tabindex="-1"
      id="offcanvasRight"
      aria-labelledby="offcanvasRightLabel"
    >
      <div class="offcanvas-header">
        <button
          type="button"
          class="btn-close"
          data-bs-dismiss="offcanvas"
          aria-label="Close"
        ></button>
      </div>
      <div class="offcanvas-body">
        <ul class="nav justify-content-center">
          <li class="nav-item">
            <a class="nav-link" aria-current="page" href="#">HOME</a>
          </li>
          <li class="nav-item btn-effect">
            <a class="nav-link" aria-current="page" href="#about">À PROPOS</a>
          </li>
          <li class="nav-item li-group" role="group">
            <ul class="intern">
              <li class="nav-item">SERVICES</li>
              <hr />
              <li class="item nav-item">
                <a class="dropdown-item" href="#turnkey-ctr">Solution "Clé en main"</a>
              </li>
              <li class="item nav-item">
                <a class="dropdown-item" href="#bespoke-ctr">Solution Sur-mesure</a>
              </li>
            </ul>
          </li>
          <li class="nav-item">
            <a class="nav-link" href="#contact">CONTACT</a>
          </li>
        </ul>
      </div>
    </div>
  </div>
</template>

<style lang="scss">
.navbar {
  transform: translateY(-195px);
  animation: deployeNav 1s 0.5s forwards;
  position: fixed;
  z-index: 1;
  top: 10px;
  .navbar-brand {
    position: fixed;
    top: -15px;
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

//MOBILE NAV
#navbar-mobile {
  justify-content: flex-end;
  z-index: 3;
  transform: translateY(0px);
  animation: none;
  .btn-offcanvas {
    right: 5%;
    top: 10px;

    img {
      position: relative;
      z-index: 2;
    }
    &::before {
      content: '';
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      backdrop-filter: blur(101px);
      z-index: 1;
    }
    &:focus,
    &:active {
      border: none;
      box-shadow: none;
    }
  }

  .offcanvas {
    height: 100vh;
    width: 75%;
    .offcanvas-body .nav {
      height: 100%;
      display: flex;
      flex-direction: column;
      align-items: flex-end;
      justify-content: flex-start !important;
      .li-group {
        display: flex;
        flex-direction: column;
        align-items: flex-end;
        ul.intern {
          padding: 0;
          margin: 0;
          text-align: right;
          .item {
            font-size: medium;
          }
        }
      }
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
</style>