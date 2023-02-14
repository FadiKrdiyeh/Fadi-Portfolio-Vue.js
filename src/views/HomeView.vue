<template>
  <div class="home">
    <div class="row">
      <div class="col-md-4 d-none d-md-flex">
        <div class="coder">&lt;coder /&gt;</div>
      </div>
      <div class="col-md-4">
        <img
          class="my-image rounded-circle"
          src="../assets/me.jpg"
          alt="Image"
        />
      </div>
      <div class="col-md-4 d-none d-md-flex">
        <pre class="code">
          <vue-writer :array="[code]" :iterations="1" :typeSpeed="1" :start="500" />
        </pre>
      </div>
      <div class="col-md-12 text-center name-skills">
        <h3 class="my-name">
          <vue-writer
            :array="[$t('homePage.Fadi Krdiyeh')]"
            :iterations="1"
            :start="4000"
          />
        </h3>
        <p class="my-skills">
          <vue-writer
            :array="text1"
            :delay="2000"
            :start="6000"
            :typeSpeed="100"
          />
        </p>
      </div>
      <div class="col-12 about-me-container">
        <div
          :class="`about-me-home ${
            $i18n.locale === 'ar' ? 'text-end' : 'text-start'
          }`"
        >
          <h3 class="about-me-title">
            {{ $t("homePage.About") }} <span>{{ $t("homePage.Me") }}</span>
          </h3>
          <p class="about-me-text">
            {{ $t("homePage.About me text", { msg: myAge }) }}
          </p>
        </div>
      </div>
      <section class="contact-me">
        <ul class="contact-list">
          <li
            class="social-item"
            :data-contact="`${$t('homePage.Facebook:')}<br />Fadi Krdiyeh`"
            @mouseenter="socialHover"
            @mouseleave="socialUnHover"
          >
            <a href="https://www.facebook.com/Fadi.Krdiyeh/"
              ><font-awesome-icon
                class="skill-icons"
                :icon="{ prefix: 'fab', iconName: 'facebook-f' }"
            /></a>
          </li>
          <li
            class="social-item"
            :data-contact="`${$t(
              'homePage.Telegram:'
            )}<br />fadi_krdiyeh / +963-938 123 636`"
            @mouseenter="socialHover"
            @mouseleave="socialUnHover"
          >
            <a href="#"
              ><font-awesome-icon
                class="skill-icons"
                :icon="{ prefix: 'fab', iconName: 'telegram' }"
            /></a>
          </li>
          <li
            class="social-item"
            :data-contact="`${$t('homePage.Instagram:')}<br />fadi_krdiyeh`"
            @mouseenter="socialHover"
            @mouseleave="socialUnHover"
          >
            <a href="https://www.instagram.com/fadi_krdiyeh/"
              ><font-awesome-icon
                class="skill-icons"
                :icon="{ prefix: 'fab', iconName: 'instagram' }"
            /></a>
          </li>
          <li
            class="social-item"
            :data-contact="`${$t('homePage.E-mail:')} <br />fadi6ka@gmail.com`"
            @mouseenter="socialHover"
            @mouseleave="socialUnHover"
          >
            <a href="#"
              ><font-awesome-icon
                class="skill-icons"
                :icon="{ prefix: 'fab', iconName: 'google' }"
            /></a>
          </li>
          <li
            class="social-item"
            :data-contact="`${$t(
              'homePage.WhatsApp And Phone Number:'
            )}<br />+963-938 123 636`"
            @mouseenter="socialHover"
            @mouseleave="socialUnHover"
          >
            <a href="#"
              ><font-awesome-icon
                class="skill-icons"
                :icon="{ prefix: 'fab', iconName: 'whatsapp' }"
            /></a>
          </li>
        </ul>
        <div class="view-content text-center"></div>
      </section>
    </div>
  </div>
</template>

<script>
import VueWriter from "vue-writer";
import $ from "jquery";

export default {
  name: "HomeView",
  components: {
    VueWriter,
  },
  data: function () {
    return {
      code: `          $(document).ready(function () {
            $(".social-item").hover(
              function () {
                let content = $(this).attr("data-contact");
                $(".view-content").fadeOut(function () {
                  $(".view-content").html(content).fadeIn(1000);
                });
              },
              function () {
                $(".view-content").fadeOut(500, function () {
                  $(".view-content").html("");
                });
              }
            );
          });`,
      text1: [
        this.$t("homePage.Full-stack Web Developer"),
        this.$t("homePage.Web Developer"),
        this.$t("homePage.Web Designer"),
        this.$t("homePage.Front-End Developer"),
        this.$t("homePage.Back-End Developer"),
      ],
    };
  },
  methods: {
    socialHover(e) {
      let content = $(e.target).attr("data-contact");
      $(".view-content").fadeOut(function () {
        $(".view-content").html(content).fadeIn(1000);
      });
    },
    socialUnHover() {
      $(".view-content").fadeOut(500, function () {
        $(".view-content").html("");
      });
    },
  },
  computed: {
    myAge() {
      let date = new Date();
      return date.getFullYear() - 2001;
    },
  },
};
</script>

<style lang="scss" scoped>
.home {
  .row {
    .col-md-4 {
      display: flex;
      align-items: center;
      justify-content: center;
    }
  }
  padding-top: 30px;
  .coder {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100%;
    font-size: 40px;
    letter-spacing: 5px;
    position: relative;
    &::after {
      content: "<coder />";
      position: absolute;
      left: 0;
      transform-origin: bottom;
      transform: rotateX(180deg) skew(-25deg);
      line-height: 0.85em;
      background-clip: text;
      -webkit-background-clip: text;
      color: transparent;
      opacity: 0.7;
    }
    @media (min-width: 768px) and (max-width: 991px) {
      font-size: 30px;
    }
  }
  .my-image {
    max-height: 350px;
    max-width: 350px;
    border: 2px solid/ #999;
    transform: rotate(0) scale(1);
    transition: transform 1s ease-out;
    &:hover {
      transform: scale(0.9);
    }
    @media (min-width: 768px) and (max-width: 991px) {
      width: 250px;
      height: 250px;
    }
  }
  .code {
    padding: 30px 0;
    font-size: 10px;
    text-align: left;
    overflow: hidden;
  }
  .name-skills {
    margin-top: 30px;
    position: relative;
    .my-name,
    .my-skills {
      font-family: Arial, "Helvetica Neue", Helvetica, sans-serif;
    }
    .my-name {
      letter-spacing: 3px;
      font-size: 27px;
    }
    .my-skills {
      font-size: 20px;
    }
  }
  .about-me-container {
    display: flex;
    justify-content: center;
    .about-me-home {
      width: 50%;
      margin-top: 20px;
      .about-me-title {
        margin-bottom: 5px;
        font-size: 25px;
        letter-spacing: 3px;
        font-weight: bold;
      }
      .about-me-text {
        font-size: 17px;
      }
    }
  }
  .contact-me {
    box-sizing: border-box;
    margin-top: 30px;
    position: relative;
    width: 100%;
    height: 300px;
    display: flex;
    justify-content: center;
    align-items: center;
    overflow: hidden;
    &::before {
      content: "";
      position: absolute;
      width: 100%;
      height: 60%;
      bottom: 0;
      z-index: 10;
      backdrop-filter: blur(10px);
    }
    .contact-list {
      position: relative;
      display: flex;
      bottom: 37px;
      li {
        position: relative;
        list-style: none;
        margin: 10px;
        @media (max-width: 575px) {
          margin: 5px;
        }
        a {
          position: relative;
          top: 0;
          width: 80px;
          height: 80px;
          display: flex;
          justify-content: center;
          align-items: center;
          font-size: 2em;
          border-radius: 10px;
          backdrop-filter: blur(4px);
          z-index: 1;
          text-decoration: none;
          overflow: hidden;
          transition: top 0.5s, z-index 0s, transform 0.5s;
          transition-delay: 0.5s, 0.5s, 0s;
          &:hover {
            transition-delay: 0s, 0.5s, 0.5s;
            top: -40px;
            transform: translateY(50px);
            z-index: 11;
            @media (max-width: 575px) {
              top: -25px;
              transform: translateY(50px);
            }
          }
          &::before {
            content: "";
            position: absolute;
            top: 0;
            left: 0;
            width: 50px;
            height: 100%;
            transform: skewX(45deg) translateX(150px);
            transition: 0.5s;
          }
          &:hover::before {
            transform: skewX(45deg) translateX(-150px);
          }
          @media (max-width: 575px) {
            width: 50px;
            height: 50px;
            font-size: 1.5em;
          }
        }
      }
    }
    .view-content {
      position: absolute;
      font-size: 25px;
      margin-bottom: 10vh;
      bottom: 0;
      z-index: 11;
    }
  }
}
</style>
