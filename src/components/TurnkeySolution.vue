<script>
export default {
  name: 'Turnkey',
  mounted() {
    this.slideEffects()
  },
  methods: {
    slideEffects() {
      const el = document.querySelector('.work')
      const h2 = document.querySelector('.h2-work')
      const cardsL = document.querySelectorAll('.cln-l .card')
      const cardsR = document.querySelectorAll('.cln-r .card')

      document.addEventListener('scroll', () => {
        const { scrollTop, scrollHeight, clientHeight } = document.documentElement
        const topElementToTopViewport = el.getBoundingClientRect(scrollHeight).top
        if (scrollTop > (scrollTop + topElementToTopViewport).toFixed() - clientHeight * 0.6) {
          h2.classList.add('active')

          cardsL.forEach((cardL, index) => {
            setTimeout(() => {
              cardL.classList.add('slide-l') // Ajoutez une classe CSS pour déclencher l'animation
            }, 900 * index) // Appliquez un délai de 0.9 seconde multiplié par l'index de la carte
          })
          cardsR.forEach((cardR, index) => {
            setTimeout(() => {
              cardR.classList.add('slide-r') // Ajoutez une classe CSS pour déclencher l'animation
            }, 400 * index) // Appliquez un délai de 0.4 seconde multiplié par l'index de la carte
          })
        } else if (
          scrollTop >
          (scrollTop + topElementToTopViewport).toFixed() - clientHeight + 0.8
        ) {
          h2.classList.remove('active')

          cardsL.forEach((cardL, index) => {
            setTimeout(() => {
              cardL.classList.remove('slide-l') // Ajoutez une classe CSS pour déclencher l'animation
            }, 900 * index) // Appliquez un délai de 0.9 seconde multiplié par l'index de la carte
          })
          cardsR.forEach((cardR, index) => {
            setTimeout(() => {
              cardR.classList.remove('slide-r') // Ajoutez une classe CSS pour déclencher l'animation
            }, 400 * index) // Appliquez un délai de 0.4 seconde multiplié par l'index de la carte
          })
        }
      })
    }
  }
}
</script>

<template>
  <div id="turnkey-solution" class="work container">
    <h2 class="h2-work">• Profitez d'une solution "clé en main" •</h2>
    <span class="def">
      <p>
        Un site web "clé en main" est un concept où un ensemble de fonctionnalités et de designs
        préconçus vous sont proposés pour créer rapidement votre site web. L'idée est de simplifier
        le processus de création de site en offrant des solutions pré-faites, prêtes à être
        utilisées avec peu ou pas de personnalisation requise.
      </p>
      <p style="font-weight: 700">ESSAYEZ-LES!</p>
    </span>
    <div class="row">
      <div class="col-sm-12 col-lg-6 cln cln-l">
        <div class="card">
          <img class="" src="../assets/images/DITO2.png" alt="Card image cap" />
          <i id="headlining" class="bi bi-bookmark-star-fill" data-v-3309a9c7=""></i>
          <div class="card-body">
            <h3>DITO PRO</h3>
            <p>
              Réalisation d'un site vitrine de dépannage informatique pour l'entreprise DITO-PRO et
              déploiement du site sur OVHCloud
            </p>
            <div class="card-footer">
              <button class="btn">
                <a href="https://dito-pro.fr/"
                  >Découvrir <i class="bi bi-box-arrow-up-right"></i
                ></a>
              </button>
            </div>
          </div>
        </div>
        <div class="card">
          <img class="" src="../assets/images/GROUPOMANIA.png" alt="Card image cap" />
          <div class="card-body">
            <h3>GROUPOMANIA</h3>
            <p>Réalisation d'un réseau social d'entreprise et d'une base de données SQL</p>
            <div class="card-footer">
              <button class="btn">
                <a href="https://clarallbt.github.io/GrpMVP2.0/"
                  >Découvrir <i class="bi bi-box-arrow-up-right"></i
                ></a>
              </button>
            </div>
          </div>
        </div>
        <div class="card">
          <img class="" src="../assets/images/FABRIQUE.png" alt="Card image cap" />
          <div class="card-body">
            <h3>PIIQUANTE</h3>
            <p>Développement d'une API sécurisée pour une application d'avis gastronomiques</p>
            <div class="card-footer">
              <button class="btn">
                <a href="https://clarallbt.github.io/PIIQUANTE/"
                  >Découvrir <i class="bi bi-box-arrow-up-right"></i
                ></a>
              </button>
            </div>
          </div>
        </div>
      </div>
      <div class="col-sm-12 col-lg-6 cln cln-r">
        <div class="card">
          <img class="" src="../assets/images/ORINOCO.png" alt="Card image cap" />
          <div class="card-body">
            <h3>ORINOCO</h3>
            <p>Construire un site e-commerce pour la vente d'appareils photos</p>
            <div class="card-footer">
              <button class="btn">
                <a href="https://clarallbt.github.io/Orinoco/"
                  >Découvrir <i class="bi bi-box-arrow-up-right"></i
                ></a>
              </button>
            </div>
          </div>
        </div>
        <div class="card">
          <img class="" src="../assets/images/OhMyFood.png" alt="Card image cap" />
          <div class="card-body">
            <h3>OH MY FOOD</h3>
            <p>
              Intégrer du contenu conformément à une maquette en mettant en oeuvre des effets CSS
              graphiques avancés
            </p>
            <div class="card-footer">
              <button class="btn">
                <a href="https://clarallbt.github.io/OhMyFood---OC-/"
                  >Découvrir <i class="bi bi-box-arrow-up-right"></i
                ></a>
              </button>
            </div>
          </div>
        </div>
        <div class="card">
          <img class="" src="../assets/images/mockup_reservia.png" alt="Card image cap" />
          <div class="card-body">
            <h3>RESERVIA</h3>
            <p>
              Création d'une page d'accueil responsive pour une agence de voyage en intégrant du
              contenu conformément à une maquette
            </p>
            <div class="card-footer">
              <button class="btn">
                <a href="https://clarallbt.github.io/Reservia---OC-/"
                  >Découvrir <i class="bi bi-box-arrow-up-right"></i
                ></a>
              </button>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.work {
  overflow: hidden;
  margin-top: 50px;
  h2 {
    text-align: center;
    margin: 50px 0;
    width: 100%;
    transform: translateX(-1000px);
    opacity: 0;
    letter-spacing: 15px;
    /* border-bottom: 1px black solid; */
  }
  h2::after {
    display: block;
    content: '';
    width: 100%;
    padding: 15px 0;
    border-bottom: 1px black solid;
  }
  h2.active {
    animation: titleSlide 0.5s forwards;
  }
  h2.desactive {
    animation: titleSlide 0.5s reverse;
  }
  span {
    p {
      font-size: large;
      text-align: center;
    }
  }
  //Cards Design
  .card #headlining {
    position: absolute;
    font-size: 60px;
    top: -17px;
    left: -9px;
  }
  .cln-l .card {
    float: right;
  }
  .cln-r .card {
    float: left;
  }
  .card {
    width: 80%;
    margin: 10px auto;
    overflow: hidden;
    transform: translateY(300px);
    opacity: 0;
    .card-body {
      position: absolute;
      bottom: 0;
      color: white;
      opacity: 0;
      z-index: 2;
      transform: translateY(50px);
      p {
        font-size: 17px;
      }
      .card-footer {
        padding-left: 0;
        .btn {
          padding-left: 0;
          font-size: x-large;
          a {
            background: linear-gradient(
              #cfc09f -87%,
              #634f30 -71%,
              #cfc09f -3%,
              #ffecb3 31%,
              #3a2c0f 144%
            );
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            font-weight: bolder;
            i {
              font-size: 20px;
            }
            &:focus {
              border: none;
            }
            &:focus,
            &:active {
              border-color: none;
            }
          }
        }
      }
    }
    &:hover {
      img {
        filter: blur(2px);
      }
      .card-body {
        transform: translateY(0px);
        transition: transform 1.2s ease, opacity 1.4s ease;
        opacity: 1;
      }
    }

    &:hover::after {
      content: '';
      pointer-events: none;
      position: absolute;
      z-index: 1;
      inset: 0px;
      opacity: 0.8;
      background: linear-gradient(rgba(0, 0, 0, 0.1) -10%, rgb(0 0 0 / 92%) 80%);
    }
  }
  //Cards Animations
  .cln-l .card.slide-l {
    animation: slideCards 0.8s forwards;
  }
  .cln-r .card.slide-r {
    animation: slideCards 0.8s forwards;
  }
}

// Animations
@keyframes titleSlide {
  0% {
    transform: scale(0.5);
    opacity: 0;
  }
  100% {
    transform: translate(0);
    opacity: 1;
  }
}
@keyframes slideCards {
  0% {
    transform: translateY(300px);
    opacity: 0;
  }
  100% {
    transform: translateY(0);
    opacity: 1;
  }
}
</style>