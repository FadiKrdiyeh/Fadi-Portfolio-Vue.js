<template>
  <div class="error">
    <div class="row error-container">
      <div class="circles">
        <p>
          404
          <br />
          <small>{{ $t("error.PAGE NOT FOUND") }}</small>
        </p>
        <span class="circle big"></span>
        <span class="circle med"></span>
        <span class="circle small"></span>
        <br />
        <br />

        <div class="contact-btn submit buttons-width">
          <button class="submit-btn-item">
            <router-link to="/">
              <font-awesome-icon
                class="back-icon pe-2"
                :icon="{ prefix: 'far', iconName: 'arrow-alt-circle-left' }"
              />
              <span>{{ $t("error.Home") }}</span>
            </router-link>
          </button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "ErrorView",
};
</script>

<style lang="scss" scoped>
.error {
  .error-container {
    justify-content: center;
    align-items: center;
    margin-top: 20px;
    padding-top: 10px;
    .circles {
      text-align: center;
      position: relative;
      &:after {
        content: "";
        display: inline-block;
        width: 100%;
        height: 100%;
        position: absolute;
        top: -50px;
        left: 0;
        transform: skewY(-4deg);
        -webkit-transform: skewY(-4deg);
      }
      p {
        font-size: 240px;
        padding-top: 90px;
        position: relative;
        z-index: 9;
        line-height: 100%;
        small {
          font-size: 40px;
          line-height: 100%;
          vertical-align: top;
        }
      }
      .circle {
        &.small {
          width: 140px;
          height: 140px;
          border-radius: 50%;
          background: rgba(179, 0, 0, 0.76);
          position: absolute;
          z-index: 1;
          top: 80px;
          left: 50%;
          animation: 7s smallmove infinite cubic-bezier(1, 0.22, 0.71, 0.98);
          -webkit-animation: 7s smallmove infinite
            cubic-bezier(1, 0.22, 0.71, 0.98);
          animation-delay: 1.2s;
          -webkit-animation-delay: 1.2s;
        }
        &.med {
          width: 200px;
          height: 200px;
          border-radius: 50%;
          background: rgba(104, 0, 0, 0.808);
          position: absolute;
          z-index: 1;
          top: 0;
          left: 10%;
          animation: 7s medmove infinite cubic-bezier(0.32, 0.04, 0.15, 0.75);
          -webkit-animation: 7s medmove infinite
            cubic-bezier(0.32, 0.04, 0.15, 0.75);
          animation-delay: 0.4s;
          -webkit-animation-delay: 0.4s;
        }
        &.big {
          width: 400px;
          height: 400px;
          border-radius: 50%;
          background: rgba(255, 0, 0, 0.601);
          position: absolute;
          z-index: 1;
          top: 200px;
          right: 0;
          animation: 8s bigmove infinite;
          -webkit-animation: 8s bigmove infinite;
          animation-delay: 3s;
          -webkit-animation-delay: 1s;
        }
      }
      .contact-btn {
        position: relative;
        width: 175px;
        height: 50px;
        margin: 20px auto;
        .submit-btn-item {
          position: absolute;
          top: 0;
          left: 0;
          width: 100%;
          height: 100%;
          display: flex;
          justify-content: center;
          align-items: center;
          border-radius: 30px;
          z-index: 1;
          font-weight: 400;
          letter-spacing: 1px;
          overflow: hidden;
          transition: 0.3s;
          backdrop-filter: blur(15px);
          &::before {
            content: "";
            position: absolute;
            top: 0;
            left: 0;
            width: 50%;
            height: 100%;
            transform: skewX(45deg) translateX(0);
            transition: 0.5s;
          }
          a {
            text-decoration: none;
          }
        }
        &:hover {
          .submit-btn-item {
            letter-spacing: 3px;
            &::before {
              transform: skewX(45deg) translateX(200%);
            }
          }
          &::before {
            bottom: 0;
            height: 50%;
            width: 80%;
            border-radius: 30px;
            transition-delay: 0.3s;
          }
          &::after {
            top: 0;
            height: 50%;
            width: 80%;
            border-radius: 30px;
            transition-delay: 0.3s;
          }
        }
        &::before {
          content: "";
          position: absolute;
          left: 50%;
          transform: translateX(-50%);
          bottom: -5px;
          width: 30px;
          height: 10px;
          border-radius: 10px;
          transition: 0.3s;
          transition-delay: 0s;
        }
        &::after {
          content: "";
          position: absolute;
          left: 50%;
          transform: translateX(-50%);
          top: -5px;
          width: 30px;
          height: 10px;
          border-radius: 10px;
          transition: 0.3s;
          transition-delay: 0s;
        }
      }
    }

    @-webkit-keyframes smallmove {
      0% {
        top: 10px;
        left: 45%;
        opacity: 1;
      }
      25% {
        top: 300px;
        left: 40%;
        opacity: 0.7;
      }
      50% {
        top: 240px;
        left: 55%;
        opacity: 0.4;
      }
      75% {
        top: 100px;
        left: 40%;
        opacity: 0.6;
      }
      100% {
        top: 10px;
        left: 45%;
        opacity: 1;
      }
    }
    @keyframes smallmove {
      0% {
        top: 10px;
        left: 45%;
        opacity: 1;
      }
      25% {
        top: 300px;
        left: 40%;
        opacity: 0.7;
      }
      50% {
        top: 240px;
        left: 55%;
        opacity: 0.4;
      }
      75% {
        top: 100px;
        left: 40%;
        opacity: 0.6;
      }
      100% {
        top: 10px;
        left: 45%;
        opacity: 1;
      }
    }

    @-webkit-keyframes medmove {
      0% {
        top: 0px;
        left: 20%;
        opacity: 1;
      }
      25% {
        top: 300px;
        left: 80%;
        opacity: 0.7;
      }
      50% {
        top: 240px;
        left: 55%;
        opacity: 0.4;
      }
      75% {
        top: 100px;
        left: 40%;
        opacity: 0.6;
      }
      100% {
        top: 0px;
        left: 20%;
        opacity: 1;
      }
    }

    @keyframes medmove {
      0% {
        top: 0px;
        left: 20%;
        opacity: 1;
      }
      25% {
        top: 300px;
        left: 80%;
        opacity: 0.7;
      }
      50% {
        top: 240px;
        left: 55%;
        opacity: 0.4;
      }
      75% {
        top: 100px;
        left: 40%;
        opacity: 0.6;
      }
      100% {
        top: 0px;
        left: 20%;
        opacity: 1;
      }
    }

    @-webkit-keyframes bigmove {
      0% {
        top: 0px;
        right: 4%;
        opacity: 0.5;
      }
      25% {
        top: 100px;
        right: 40%;
        opacity: 0.4;
      }
      50% {
        top: 240px;
        right: 45%;
        opacity: 0.8;
      }
      75% {
        top: 100px;
        right: 35%;
        opacity: 0.6;
      }
      100% {
        top: 0px;
        right: 4%;
        opacity: 0.5;
      }
    }
    @keyframes bigmove {
      0% {
        top: 0px;
        right: 4%;
        opacity: 0.5;
      }
      25% {
        top: 100px;
        right: 40%;
        opacity: 0.4;
      }
      50% {
        top: 240px;
        right: 45%;
        opacity: 0.8;
      }
      75% {
        top: 100px;
        right: 35%;
        opacity: 0.6;
      }
      100% {
        top: 0px;
        right: 4%;
        opacity: 0.5;
      }
    }
  }
}
</style>
