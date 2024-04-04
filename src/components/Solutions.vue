<script>
export default {
  name: 'Solutions',
  mounted() {
    this.slideEffects()
  },
  methods: {
    slideEffects() {
      const el = document.querySelector('.solutions')
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
  <div class="container solutions">
    <div id="turnkey-ctr" class="row turnkey-ctr">
      <div class="col-12 col-md-5 txt">
        <h2 class="h2-work">Solution immédiate</h2>
        <p>Profitez d'une solution "clé en main"</p>
        <span class="def">
          <p>
            Un site web "clé en main" est un concept où un ensemble de fonctionnalités et de designs
            préconçus vous sont proposés pour créer rapidement votre site web. L'idée est de
            simplifier le processus de création de site en offrant des solutions pré-faites, prêtes
            à être utilisées avec peu ou pas de personnalisation requise.
          </p>
          <p class="asterisk">
            <i class="bi bi-asterisk"></i> Veuillez noter que les templates qui vous sont proposés
            ici présentent des entreprises fictives. Ces démonstrations vous offrent un aperçu
            immersif de ce que votre entreprise pourrait être en ligne.
          </p>
          <button class="btn btn-effect" style="font-weight: 700">
            ESSAYEZ-LES! <i class="bi bi-arrow-right"></i>
          </button>
        </span>
      </div>
      <div class="col-12 col-md-7 preview">
        <div class="row">
          <div class="col-sm-12 col-lg-6 cln cln-l">
            <div class="card">
              <img class="" src="../assets/images/ORINOCO.png" alt="Card image cap" />
              <div class="card-body">
                <h3>ORINOCO</h3>
                <p>Template Site web E-commerce</p>
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
              <img class="" src="../assets/images/FABRIQUE.png" alt="Card image cap" />
              <div class="card-body">
                <h3>La Fabrique à Muffins</h3>
                <p>Template Site vitrine</p>
                <div class="card-footer">
                  <button class="btn">
                    <a href="https://clarallbt.github.io/PIIQUANTE/"
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
                <p>Template Réseau social d'entreprise</p>
                <div class="card-footer">
                  <button class="btn">
                    <a href="https://clarallbt.github.io/GrpMVP2.0/"
                      >Découvrir <i class="bi bi-box-arrow-up-right"></i
                    ></a>
                  </button>
                </div>
              </div>
            </div>
          </div>
          <div class="col-sm-12 col-lg-6 cln cln-r">
            <div class="card">
              <img class="" src="../assets/images/OhMyFood.png" alt="Card image cap" />
              <div class="card-body">
                <h3>OH MY FOOD</h3>
                <p>Template Site de commande en ligne</p>
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
                <p>Template Site Vitrine</p>
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
    </div>
    <div id="bespoke-ctr" class="row bespoke-ctr">
      <div class="col-12 col-md-5 preview">
        <div class="row slider">
          <div class="bckgd"></div>
          <div class="slide-track">
            <div class="slide">
              <img src="../assets/images/dito/DESKTOP - ARTICLESHEET.png" />
            </div>
            <div class="slide">
              <img src="../assets/images/dito/DESKTOP - CALENDAR.png" />
            </div>
            <div class="slide">
              <img src="../assets/images/dito/DESKTOP - CRUD CREATE.png" />
            </div>
            <div class="slide">
              <img src="../assets/images/dito/DESKTOP - GOOGLEREVIEWS.png" />
            </div>
          </div>
        </div>
      </div>
      <div class="col-12 col-md-7 txt">
        <h2 class="h2-work">Solution Sur-mesure</h2>
        <span>
          <p>
            Choissisez la conception sur mesure pour la création d'un site web spécifique à vos
            besoins, à vos objectifs et à l'identité de votre entreprise. Contrairement à
            l'utilisation de modèles préfabriqués ou de plateformes de création de sites web
            génériques, la conception web sur mesure offre un niveau élevé de personnalisation et de
            contrôle.
          </p>
          <button class="btn btn-effect">
            <a href="https://dito-pro.fr" style="font-weight: 700"
              >Découvrez notre dernier projet</a
            >
          </button>
        </span>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.solutions {
  .turnkey-ctr,
  .bespoke-ctr {
    margin-bottom: 80px;
    .preview {
      padding: 0;
    }
    .txt {
      display: flex;
      flex-direction: column;
      justify-content: center;
      h2 {
        letter-spacing: -2px;
        font-size: xxx-large;
        font-weight: 900;
      }
      p {
        font-size: x-large;
      }
      span p {
        font-size: medium;
      }
    }
  }
  .turnkey-ctr {
    .txt {
      h2 {
        transform: translateX(-1000px);
        opacity: 0;
        /* border-bottom: 1px black solid; */
      }
      h2.active {
        animation: titleSlide 0.5s forwards;
      }
      h2.desactive {
        animation: titleSlide 0.5s reverse;
      }
      p.asterisk {
        font-size: smaller;
      }
      .btn {
        font-size: 20px;
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
        width: 100%;
        padding: 10px;
        h3 {
          margin: 0;
          font-size: x-large;
          letter-spacing: -2px;
        }
        p {
          font-size: 16px;
          margin: 0;
        }
        .card-footer {
          padding: 0;
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
  .bespoke-ctr {
    height: 500px;
    background: #f6f7f8;
    .txt {
      .btn a {
        font-size: 20px;
      }
    }
    .slider {
      height: 100%;
      width: 100%;
      position: relative;
      margin: auto;
      overflow: hidden;
      position: relative;
      .bckgd {
        position: absolute;
        background: url('../assets/images/DITO.png');
        height: 100%;
        opacity: 80%;
        background-size: cover;
        background-position: center;
        &::before {
          content: '';
          position: absolute;
          top: 0;
          left: 0;
          width: 100%;
          height: 100%;
          backdrop-filter: blur(8px);
        }
      }
      .slide-track {
        z-index: 1;
      }
      &::before,
      &::after {
        content: '';
        height: 100px;
        position: absolute;
        width: 200px;
        z-index: 2;
      }
      &::after {
        right: 0;
        top: 0;
        transform: rotateZ(180deg);
      }

      &::before {
        left: 0;
        top: 0;
      }
      .slide-track {
        animation: scroll 40s linear infinite;
        display: flex;
        width: calc(250px * 4);
      }
      .slide {
        height: 100%;
        width: 465px;
        display: flex;
        align-items: center;
        margin: 0 2px;
        img {
          width: inherit;
        }
      }
    }
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
@keyframes scroll {
  0% {
    transform: translateX(0);
  }
  100% {
    transform: translateX(calc(-250px * 4));
  }
}
</style>