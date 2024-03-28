<script>
import Banner from '@/components/Banner.vue'
import Navbar from '@/components/Navbar.vue'
import TurnKeySolution from '../components/TurnkeySolution.vue'
import Contact from '@/components/Contact.vue'
import References from '../components/References.vue'

export default {
  name: 'Home',
  components: { Banner, Navbar, TurnKeySolution, Contact, References },
  mounted() {
    const hexElements = document.querySelectorAll('.hex')
    const hasAnimation = document.querySelectorAll('.has-animation')
    const networksLink = document.querySelector('.networks-link')

    if (document.readyState != 200) {
      hasAnimation[0].classList.add('animate-in')
      // networksLink.classList.add('animate')
      hexElements.forEach((hex, index) => {
        setTimeout(() => {
          // Ajoutez une classe CSS pour déclencher l'animation
          hex.classList.add('show')
          document.addEventListener('scroll', () => {
            const { scrollTop, scrollHeight, clientHeight } = document.documentElement
            const topElementToTopViewport = hex.getBoundingClientRect(scrollHeight).top
          })
        }, 500 * index) // Appliquez un délai de 0.5 seconde multiplié par l'index de la carte
      })
    }
  }
}
</script>

<template>
  <img class="bckgd-top" src="../assets/images/white-hewagone-form.png" alt="" />
  <Navbar />

  <div class="container-fluid banner-ctr">
    <div class="row titles">
      <div class="col-5 main-title has-animation" style="text-align: end">
        <h1>Boostez votre présence en ligne avec Kala Develops</h1>
        <p>Services de développement web</p>
        <div class="networks-link">
          <ul>
            <li>
              <a href="https://linkedin.com/in/cllbt"><i class="bi bi-linkedin"></i></a>
            </li>
            <li>
              <a href="https://www.facebook.com/profile.php?id=100069904156077"
                ><i class="bi bi-facebook"></i
              ></a>
            </li>
            <li>
              <a href="https://www.instagram.com/kala__dev/"><i class="bi bi-instagram"></i></a>
            </li>
          </ul>
        </div>
      </div>
      <div class="col-3 hex">
        <div class="img"></div>
      </div>
    </div>
    <div class="row turnkey-solution">
      <div class="col-4 hex intro">
        <span>
          <h2>Solution clé en main</h2>
          <p>
            Des sites web clés en main, prêts à briller en un clic ! Découvrez notre sélection de
            designs élégants et professionnels, conçus pour vous faire économiser du temps et de
            l'argent. Obtenez une présence en ligne de qualité à prix compétitifs.
          </p>
          <button class="btn"><a href="#turnkey-solution">En Savoir plus</a></button>
        </span>
      </div>
      <div class="col-4 hex preview">
        <div class="slider">
          <span class="slide-track">
            <div class="slide">
              <img src="../assets/images/ORINOCO.png" alt="" />
            </div>
            <div class="slide">
              <img src="../assets/images/FABRIQUE.png" alt="" />
            </div>
            <div class="slide"></div>
            <img src="../assets/images/GROUPOMANIA.png" alt="" />
            <div class="slide">
              <img src="../assets/images/OhMyFood.png" alt="" />
            </div>
          </span>
        </div>
      </div>
    </div>
    <div class="row bespoke-solution">
      <div class="col-4 hex intro">
        <span>
          <h2>Solution sur-mesure</h2>
          <ul class="list">
            <li>Conception sur-mesure</li>
            <li>Expertise Fullstack</li>
            <li>Optimisation mobile</li>
            <li>SEO</li>
          </ul>
          <button class="btn"><a href="#turnkey-solution">En Savoir plus</a></button>
        </span>
      </div>
      <div class="col-4 hex preview">
        <span class="round-border"> </span>
      </div>
    </div>
  </div>

  <TurnKeySolution />
  <References />

  <Contact />
  <footer id="footer" class="container-fluid">
    <p>
      Copyright©2023 KALADEV - <i class="bi bi-geo-alt-fill"></i> Boulogne-sur-Mer -
      <router-link to="/CGV">CGV</router-link> -
      <router-link to="/MentionsLegales">Mentions légales</router-link>
    </p>
  </footer>
</template>

<style lang="scss">
.bckgd-top {
  position: absolute;
  transform: rotate(180deg);
  top: 0;
  right: 0;
  z-index: -1;
  opacity: 20%;
  width: 50%;
}
.hex {
  transform: translateY(300px);
  opacity: 0;
}
.hex.show {
  transform: translateY(0);
  opacity: 1;
  transition: transform 0.5s ease-in-out, opacity 0.3s ease-in;
}
.has-animation {
  position: relative;
  margin: 10px;
  h1,
  p {
    opacity: 0;
  }
  p {
    font-size: 20px;
  }
  &.animate-in {
    h1 {
      animation: textHidden 2s ease forwards;
    }
    p {
      animation: textHidden 2s 0.5s ease forwards;
    }
  }
}

.banner-ctr {
  display: flex;
  flex-direction: column;
  margin-top: 150px;
  .titles {
    justify-content: center;
    .main-title {
      align-self: center;
    }
    .networks-link {
      // opacity: 0;
      // &.animate {
      //   animation: textHidden 2s 1.5s ease forwards;
      // }
      ul {
        padding: 0;
        list-style: none;
        display: inline-flex;
        width: 30%;
        justify-content: space-between;
        li {
          margin: 0 5px;
          font-size: xx-large;
        }
      }
    }
    .hex {
      .img {
        background: url(/src/assets/images/medias.png);
        height: 400px;
        position: absolute;
        background-size: contain;
        background-repeat: no-repeat;
        background-position: center;
        top: 0;
        left: 0;
        right: 0;
        bottom: 0;
        margin: auto;
      }
    }
  }
  .turnkey-solution {
    align-self: center;
    justify-content: left;
    position: relative;
    top: -152px;
    right: 49px;
    .intro span {
      position: absolute;
      height: 100%;
      display: flex;
      flex-direction: column;
      justify-content: center;
      padding: 50px;
      text-align: center;
      font-size: 21px;
      align-items: center;
      .btn {
        background: linear-gradient(57deg, #ab9c7c, #cfc09f, #ffecb3, #cfc09f);
        width: max-content;
        a {
          color: white;
        }
      }
    }
    .preview {
      position: relative;
      .slider {
        position: absolute;
        top: 0;
        width: 100%;
        height: 100%;
        clip-path: polygon(50% 0%, 147% 50%, 50% 100%, -48% 50%);

        .slide-track {
          flex-direction: column;
          justify-content: center;
          padding: 30px;
          animation: scroll 40s linear infinite;
          display: flex;
          height: calc(100% * 4);
        }

        .slide {
          height: max-content;
          width: 100%;
          padding-bottom: 5px;
          img {
            width: 100%;
            z-index: -1;
          }
        }
      }
      span {
        text-align: end;
        width: 100%;
        height: 100%;
      }
    }
  }
  .bespoke-solution {
    align-self: center;
    justify-content: center;
    position: relative;
    top: -305px;
    right: -142px;
    .intro span {
      position: absolute;
      height: 100%;
      width: 100%;
      display: flex;
      flex-direction: column;
      justify-content: center;
      text-align: center;
      align-items: center;
      ul {
        font-size: x-large;
        padding: 0;
      }
      .btn {
        background: linear-gradient(57deg, #ab9c7c, #cfc09f, #ffecb3, #cfc09f);
        width: max-content;
        a {
          color: white;
        }
      }
    }
    .preview span {
      position: absolute;
      top: 0px;
      width: 100%;
      height: 100%;
      clip-path: polygon(50% 0%, 147% 50%, 50% 100%, -47% 50%);
      padding: 4px;
      border-radius: 20px;
      border: 6px solid #fff;
      background: url('../assets/images/DITO2.png');
      background-position: top;
      background-size: cover;
    }
  }
}
footer {
  text-align: center;
}
//ANIMATIONS KEYFRAMES

@keyframes textHidden {
  0% {
    opacity: 0;
  }
  100% {
    opacity: 1;
  }
}

// Animation
@keyframes scroll {
  0% {
    transform: translateY(0);
  }
  100% {
    transform: translateY(calc(-250px * 7));
  }
}
</style>
