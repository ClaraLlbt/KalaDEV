
<script>
export default {
  name: 'DevBanner'
}
</script>

<template>
  <div class="container-fluid banner-ctr">
    <div class="row titles">
      <div class="col-4">
        <img src="../assets/images/medias.png" alt="" />
      </div>
      <div class="col-4 main-title" style="text-align: end">
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
    </div>
    <div class="row business-services">
      <div class="col-6 hexagon turnkey-solution">
        <span
          >Des sites web clés en main, prêts à briller en un clic ! Découvrez notre sélection de
          designs élégants et professionnels, conçus pour vous faire économiser du temps et de
          l'argent. Obtenez une présence en ligne de qualité à prix compétitifs.
          <button class="btn"><a href="#turnkey-solution">En Savoir plus</a></button>
        </span>
      </div>
      <div class="col-6 bespoke-solution">
        <span>
          <h2>Décidez d’opter pour du sur-mesure</h2>
          <ul class="list">
            <li>Conception sur-mesure</li>
            <li>Expertise Fullstack</li>
            <li>Optimisation mobile</li>
            <li>SEO</li>
          </ul>
        </span>
      </div>
    </div>
  </div>
</template>


<style lang="scss" scoped>
.banner-ctr {
  height: 100vh;
  display: flex;
  flex-direction: column;
  justify-content: flex-end;
  .titles {
    justify-content: space-evenly;
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
  }
  .business-services {
    position: relative;
    &::before {
      content: '';
      position: absolute;
      top: 0;
      bottom: 0;
      left: 0;
      right: 0;
      background: linear-gradient(
        132deg,
        rgb(226, 226, 226) 0%,
        rgb(248, 248, 248) 52%,
        rgb(226, 226, 226) 100%
      );
      z-index: -1;
      opacity: 60%;
    }
    .turnkey-solution {
      padding: 50px;
      text-align: center;
      font-size: larger;
      position: relative;
      &::before {
        content: '';
        position: absolute;
        top: 0;
        bottom: 0;
        left: 0;
        right: 0;
        background: linear-gradient(132deg, #bab9c4 0%, #d6d6d6 52%, #bab9c4 100%);
        border-top-right-radius: 50px;
        z-index: -1;
        opacity: 60%;
      }
      span {
        font-weight: 700;
        display: flex;
        flex-direction: column;
        width: 70%;
        margin: auto;
        .btn {
          background: linear-gradient(57deg, #ab9c7c, #cfc09f, #ffecb3, #cfc09f);
          width: max-content;
          margin: 50px auto;
          a {
            color: white;
          }
        }
      }
    }
    .bespoke-solution {
      span {
        padding: 50px;
        width: 80%;
        display: flex;
        flex-direction: column;
        align-items: flex-end;
        margin: auto;
        color: gray;
        .list {
          list-style: none;
          font-size: x-large;
          li {
            text-align: end;
          }
        }
      }
    }
  }
}
</style>