<script>
import Navbar from '@/components/Navbar.vue'
import Contact from '@/components/Contact.vue'
import Solutions from '@/components/Solutions.vue'
import Loader from '@/components/Loader.vue'
import About from '@/components/About.vue'

export default {
  name: 'Home',
  components: { Navbar, Contact, Solutions, Loader, About },
  data() {
    return {
      loaderElement: true
    }
  },
  created() {
    setTimeout(() => {
      if (document.readyState != 200) {
        console.log("Hello, l'application vient de se lancer")
        this.loaderElement = !this.loaderElement
      }
    }, 3000)
  },
  beforeUpdate() {
    const hexElements = document.querySelectorAll('.hex')
    const hasAnimation = document.querySelectorAll('.has-animation')
    const networksLink = document.querySelector('.networks-link')

    if (document.readyState != 200) {
      hasAnimation[0].classList.add('animate')
      hasAnimation[1].classList.add('animate-in')
      // networksLink.classList.add('animate')
      hexElements.forEach((hex, index) => {
        setTimeout(() => {
          // Ajoutez une classe CSS pour déclencher l'animation
          hex.classList.add('show')
          document.addEventListener('scroll', () => {
            const { scrollTop, scrollHeight, clientHeight } = document.documentElement
            const topElementToTopViewport = hex.getBoundingClientRect(scrollHeight).top
          })
        }, 800 * index) // Appliquez un délai de 0.5 seconde multiplié par l'index de la carte
      })
    }
  }
}
</script>

<template>
  <img class="bckgd-top" src="../assets/images/white-hewagone-form.png" alt="" />

  <Loader v-show="loaderElement" />
  <div class="main" v-show="!loaderElement">
    <Navbar />

    <div class="container-fluid banner-ctr">
      <div class="row titles has-animation">
        <div class="col-10 col-sm-6 col-xl-4 col-xxl-3 main-title has-animation hex-content">
          <div class="hex hex-intro"></div>
          <span>
            <h1>Boostez votre présence en ligne avec Kala Develops</h1>
            <p>Services de développement web</p>
            <p>
              Ma mission est de vous aider à prospérer dans une ruche numérique en constante
              évolution.
            </p>
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
                <!-- <li>
                <a href="https://www.instagram.com/kala__dev/"><i class="bi bi-instagram"></i></a>
              </li> -->
              </ul>
            </div>
          </span>
        </div>
      </div>
      <div class="row options">
        <div class="col-6 col-sm-6 col-xl-4 col-xxl-3 hex-content turnkey">
          <div class="hex"></div>
          <span>
            <img
              src="data:image/png;base64,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"
            />
            <h3>Solution "Clé en main"</h3>
            <p>
              Des sites web clés en main, prêts à briller en un clic ! Découvrez notre sélection de
              designs élégants et professionnels, conçus pour vous faire économiser du temps et de
              l'argent. Obtenez une présence en ligne de qualité à prix compétitifs.
            </p>
            <button class="btn"><a href="#turnkey">En Savoir plus</a></button>
          </span>
        </div>
        <div class="col-6 col-sm-6 col-xl-4 col-xxl-3 hex-content bespoke">
          <div class="hex"></div>
          <span>
            <img
              src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAEAAAABACAYAAACqaXHeAAAACXBIWXMAAAsTAAALEwEAmpwYAAAB3klEQVR4nOWYQWrEMAxF/yVa6BV6/+WsEgID3bWLHqNzA5VCKKGNEztjfX1NDNqYZDJ+SE9KAGAC8AbgGSddNsdHMgjT4r8fjRF/Nj4BvCDHsk6BZQZkyoTfAxy89h+AJwDviTKhOwAkg+ACIBMENwCYHaDuhKLVN65d3bMCSXUIawCGnWtX92wjlZTLwbUEMkDoDsA26kixHNwADIUfUYNAKwFVCO5dQB0CpQsoi5EqQcVMoEtQDUKIBJXKgQZgqvhkFpEJtC5glQdjQ+jeBaxA0UQh0CRoiwMpQaA5wOZokR1DjHQAEIMQAqA1xT3LoXsXsB0JQgyCWxcYKm5WgBBWAssV6QQJAJEQZABEQXAbhMaDD2I7wa0LDBU3K0Do3gVKqwUAsxykHBABQRoAA4KcBNlOcAMw3PEgJoTuXaC07gXgBUG2C7CcIC9BbwgpJOhZDjcAX0ggQS8Ir3OkKoGoFyhJANFjswSAyLE5TIIRb5FyElQYm2VKgFEOaQB4QUgFgDU2S0nQ2wkpJMgem6VLgDE2NwNQiWsnYNUARoFDL+OyA6AWQjWArKv6e4I9KIBqMdoDA6gSozUAmFbmBPW9XSdYA4DNgUJ0b9cJdhIARQh24rj+AFDr88y4fAOZ8WI7aIVaywAAAABJRU5ErkJggg=="
            />
            <h3>Solution "Sur-mesure"</h3>
            <ul class="list">
              <li>Conception sur-mesure</li>
              <li>Expertise Fullstack</li>
              <li>Optimisation mobile</li>
              <li>SEO</li>
            </ul>
            <button class="btn"><a href="#bespoke">En savoir plus</a></button>
          </span>
        </div>
      </div>
    </div>

    <About />
    <Solutions />

    <Contact />
    <footer id="footer" class="container-fluid">
      <p>
        Copyright©2023 KALADEV - <i class="bi bi-geo-alt-fill"></i> Boulogne-sur-Mer -
        <router-link to="/CGV">CGV</router-link> -
        <router-link to="/MentionsLegales">Mentions légales</router-link>
      </p>
    </footer>
  </div>
</template>

<style lang="scss" scoped>
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
.hex-intro {
  background: #f2f3f5 !important;
}
.hex.show {
  transform: translateY(0);
  opacity: 90%;
  transition: transform 0.5s ease-in-out, opacity 0.3s ease-in;
}
.has-animation {
  position: relative;
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
  margin-top: 110px;
  padding: 0;
  .titles {
    background: url('../assets/images/BANNER.png');
    background-size: cover;
    justify-content: center;
    padding: 0;
    opacity: 0;
    &.animate {
      animation: showBanner 1s ease forwards;
      width: 100%;
      margin: auto;
    }
    .hex-content {
      span {
        position: absolute;
        top: 40px;
        left: 0;
        padding: 10px;
        letter-spacing: -2px;
        text-align: center;
        width: 100%;
        height: 100%;
        display: flex;
        flex-direction: column;
        justify-content: center;
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
            justify-content: center;
            li {
              margin: 0 5px;
              font-size: 40px;
              i::before {
                padding: 5px;
              }
            }
          }
        }
      }
    }
  }
  .options {
    justify-content: center;
    position: relative;
    top: -140px;
    width: 100%;
    margin: auto;
    .turnkey,
    .bespoke {
      span {
        position: absolute;
        top: 0;
        display: flex;
        justify-content: space-evenly;
        align-items: center;
        height: 90%;
        width: 100%;
        flex-direction: column;

        left: 0;
        i {
          padding: 10px;
          font-size: 60px;
        }
        .btn {
          background: linear-gradient(57deg, #ab9c7c, #cfc09f, #ffecb3, #cfc09f);
          width: max-content;
          a {
            color: white;
          }
        }
      }
    }
    .turnkey {
      span p {
        width: 80%;
        text-align: center;
        font-size: 18px;
      }
    }
    .bespoke {
      span ul {
        padding: 10px 0;
        li {
          font-size: 18px;
        }
      }
    }
  }
}
footer {
  text-align: center;
}
//ANIMATIONS KEYFRAMES
@keyframes showBanner {
  0% {
    opacity: 0;
  }
  100% {
    opacity: 1;
  }
}
@keyframes textHidden {
  0% {
    opacity: 0;
  }
  100% {
    opacity: 1;
  }
}
</style>
