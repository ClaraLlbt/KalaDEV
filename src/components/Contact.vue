<script>
import emailjs from 'emailjs-com'
export default {
  name: 'Contact',
  data() {
    return {
      name: '',
      lastname: '',
      phone: '',
      email: '',
      message: ''
    }
  },
  mounted() {
    this.cssEffects()
  },
  methods: {
    cssEffects() {
      document.addEventListener('scroll', () => {
        const el = document.querySelector('.contact')
        const h2 = document.getElementsByTagName('h2')

        const cardScale = document.querySelector('.contact .card')

        const { scrollTop, scrollHeight, clientHeight } = document.documentElement
        const topElementToTopViewport = el.getBoundingClientRect(scrollHeight).top

        if (scrollTop > (scrollTop + topElementToTopViewport).toFixed() - clientHeight * 0.3) {
          //  h2[1].classList.add('active')
          cardScale.classList.add('scale-in-center')
        }
      })
    },
    sendEmail() {
      const btn = document.querySelector('#sendBtn')
      const messArea = document.querySelector('#message')
      const emailArea = document.querySelector('#reply_to')
      const form = document.getElementById('form').addEventListener('submit', function (event) {
        event.preventDefault()

        btn.innerText = 'En cours...'
        const serviceID = 'service_696tmpa'
        const templateID = 'template_bhiwqld'
        const userId = 'OkYb3_3x2XbgyN8aT'

        emailjs
          .sendForm(serviceID, templateID, this, userId, {
            name: this.name,
            lastame: this.lastname,
            phone: this.phone,
            email: this.email,
            message: this.message
          })
          .then((res) => {
            btn.innerText = 'Email Envoyé'
            document.location.href = '/'
          })
          .catch((err) => {
            btn.innerText = 'Une erreur est survenue'
          })
      })
    }
  }
}
</script>

<template>
  <div id="contact" class="contact container-fluid">
    <div class="row contact-row">
      <div class="col-lg-4 col-sm-12 contact-card">
        <div class="card">
          <div class="card-title"><p>Merci de votre visite !</p></div>
          <div class="card-body icons-contact">
            <div class="col-12 icon">
              <i class="bi bi-phone-fill"></i>
              <p>06 19 04 06 19</p>
            </div>
            <div class="col-12 icon">
              <i class="bi bi-geo-alt-fill"></i>
              <p>Boulogne-Sur-Mer</p>
            </div>
          </div>
          <div class="card-footer networks-link">
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
          <!-- <div>
                    <a href="/Clarallbt/lib/web/CV_LALIBERTE_CLARA.pdf" download="">
                        <button type="button" class="btn cv-btn"><i class="bi bi-file-pdf"></i> Télécharger mon CV</button>
                    </a>
                </div> -->
        </div>
      </div>
      <div class="col-lg-6 col-sm-12 form">
        <div class="title-form">
          <h2>• KEEP IN TOUCH •</h2>
          <div class="mess-icon">
            <img src="../assets/images/paperplane.png" alt="" />
          </div>
        </div>
        <form id="form" method="POST">
          <span>
            <p>
              Vous avez le projet de développer un site web ? vous souhaitez un devis ? Je serai
              ravie d'en discuter avec vous
            </p>
          </span>
          <div class="row">
            <div class="col-12 col-lg-6">
              <input
                v-model="name"
                type="name"
                class="form-control"
                id="name"
                name="name"
                placeholder="Votre prénom"
                aria-describedby="emailHelp"
                required
              />
            </div>

            <div class="col-12 col-lg-6">
              <input
                v-model="lastname"
                type="lastname"
                class="form-control"
                id="lastname"
                name="lastname"
                placeholder="Votre Nom"
                aria-describedby="emailHelp"
                required
              />
            </div>
          </div>
          <div>
            <input
              v-model="email"
              type="email"
              class="form-control"
              id="reply_to"
              name="reply_to"
              placeholder="Laissez moi votre Email"
              aria-describedby="emailHelp"
              required
            />
          </div>
          <div>
            <input
              v-model="phone"
              type="phone"
              class="form-control"
              id="phone"
              name="phone"
              placeholder="Laissez moi votre numéro de téléphone"
              required
            />
          </div>
          <div>
            <textarea
              v-model="message"
              class="form-control"
              id="message"
              name="message"
              rows="3"
              placeholder="Ecrivez votre demande..."
              required
            ></textarea>
          </div>
          <div class="checkbox">
            <input type="checkbox" name="acceptance-41" value="1" aria-invalid="false" required />
            <p>
              En soumettant ce formulaire, j'accepte que mes données personnelles soient utilisées
              pour me recontacter. Aucun autre traitement ne sera effectué avec mes informations.
              Pour connaître et exercer vos droits, veuillez consultez
              <RouterLink to="/Politiquedeconfidentialite"
                >la politique de confidentialité</RouterLink
              >
            </p>
          </div>

          <div class="button">
            <button
              id="sendBtn"
              @click="sendEmail()"
              type="submit"
              value="Send Email"
              class="btn btn-effect"
            >
              Envoyer
            </button>
          </div>
        </form>
      </div>
    </div>
    <img class="bckgd" src="../assets/images/white-hewagone-form.png" alt="" />
  </div>
</template>

<style lang="scss">
.contact {
  position: relative;
  .contact-row {
    padding: 40px 0;
    align-items: center;
    justify-content: center;

    .contact-card {
      .card {
        width: 70%;
        margin: auto;
        opacity: 0;
        border: 1.5px inset white;
        background: linear-gradient(
          132deg,
          rgb(226, 226, 226) 0%,
          rgb(248, 248, 248) 52%,
          rgb(226, 226, 226) 100%
        );
        transition: transform 0.5s ease-in-out;
        border-radius: 16px;
        font-weight: bolder;
        .card-title {
          text-align: center;
          padding: 10px;
          p {
            font-size: x-large;
          }
        }

        .card-body {
          .icon {
            text-align: center;
            i {
              font-size: 40px;
            }
          }
        }
        .card-footer ul {
          margin: 0;
          padding: 0;
          display: flex;
          justify-content: space-evenly;
          li {
            font-size: 25px;
          }
        }
        p {
          font-size: 20px;
          color: grey;
        }
      }
      .card.scale-in-center {
        animation: scale-in-center 0.5s 0.3s cubic-bezier(0.25, 0.46, 0.45, 0.94) both;
        &:hover {
          transform: translateY(-5px);
          transition: all 0.5s ease-in-out;
        }
      }
    }
    .form {
      align-self: center;
      .title-form {
        h2 {
          letter-spacing: 15px;
          text-align: center;
          &::after {
            content: '';
            border-bottom: 1px solid black;
            width: 20%;
            display: block;
            margin: auto;
            padding: 15px;
          }
        }
        .mess-icon {
          text-align-last: center;
        }
      }
      form {
        width: 80%;
        margin: auto;
        text-align: left;
        span p {
          font-size: larger;
        }
        .form-control {
          border: none;
          border-bottom: 1px solid rgb(173, 173, 173);
          margin-bottom: 15px;
        }
        .checkbox {
          display: flex;
          align-items: baseline;
          margin: 15px auto;
          input {
            margin-right: 10px;
          }
          p {
            font-size: small;
          }
        }
        .button {
          margin-top: 30px;
          text-align: center;
        }
        .button:active {
          border: none;
        }
      }
    }
  }
  .bckgd {
    position: absolute;
    bottom: -40px;
    left: -130px;
    width: 50%;
    opacity: 40%;
    z-index: -1;
  }
}
//KEYFRAMES
@keyframes scale-in-center {
  0% {
    transform: scale(0);
    opacity: 0;
  }
  100% {
    transform: scale(1);
    opacity: 1;
  }
}
</style>