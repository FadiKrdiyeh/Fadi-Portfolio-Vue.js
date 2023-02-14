<template>
  <div class="header">
    <div class="nav">
      <div class="container">
        <nav class="navbar navbar-expand-md">
          <div class="navbar-brand">
            <div class="logo text-center">
              <span class="logo-item" id="fadi">{{ $t("header.Fadi ") }} </span>
              <span class="logo-item" id="krdiyeh">{{
                $t("header.Krdiyeh")
              }}</span>
            </div>
          </div>
          <button
            class="navbar-toggler"
            type="button"
            aria-controls="navbarSupportedContent"
            aria-expanded="false"
            aria-label="Toggle navigation"
          >
            <span class="navbar-toggler-icon">
              <font-awesome-icon
                class="skill-icons"
                :icon="{ prefix: 'fas', iconName: 'bars' }"
              />
            </span>
          </button>
          <div class="collapse navbar-collapse" id="navbarSupportedContent">
            <div
              :class="`navbar-nav nav links ${
                $i18n.locale === 'ar' ? 'me-auto' : 'ms-auto'
              }`"
            >
              <span class="nav-item nav-link close-onclick">
                <router-link
                  :class="`aaa ${
                    $i18n.locale === 'ar' ? 'text-end' : 'text-start'
                  }`"
                  to="/"
                  exact
                  >{{ $t("header.Home") }}</router-link
                >
              </span>
              <span class="nav-item nav-link close-onclick">
                <router-link
                  :class="`aaa ${
                    $i18n.locale === 'ar' ? 'text-end' : 'text-start'
                  }`"
                  to="/resume"
                  >{{ $t("header.Resume") }}</router-link
                >
              </span>
              <span class="nav-item nav-link close-onclick">
                <router-link
                  :class="`aaa ${
                    $i18n.locale === 'ar' ? 'text-end' : 'text-start'
                  }`"
                  to="/portfolio"
                  >{{ $t("header.Portfolio") }}</router-link
                >
              </span>
              <span class="nav-item nav-link close-onclick">
                <router-link
                  :class="`aaa ${
                    $i18n.locale === 'ar' ? 'text-end' : 'text-start'
                  }`"
                  to="/contact"
                  >{{ $t("header.Contact") }}</router-link
                >
              </span>
              <span class="nav-item nav-link switch-language-btn close-onclick">
                <locale-switcher />
              </span>
              <span class="nav-item nav-link switch-theme-btn close-onclick">
                <theme-switcher @switchTheme="updateTheme" />
              </span>
            </div>
          </div>
        </nav>
      </div>
    </div>
  </div>
</template>

<script>
import LocaleSwitcher from "../LocaleSwitcher.vue";
import ThemeSwitcher from "../ThemeSwitcher.vue";
import $ from "jquery";

export default {
  name: "AppHeader",
  components: {
    LocaleSwitcher,
    ThemeSwitcher,
  },
  data() {
    return {
      currentTheme: localStorage.getItem("fk-theme-color") ?? "dark-theme",
    };
  },
  methods: {
    updateTheme() {
      if (this.currentTheme == "light-theme") {
        this.$emit("switchTheme", "dark-theme");
      } else {
        this.$emit("switchTheme", "light-theme");
      }
    },
  },
};

$(document).ready(function () {
  $(".close-onclick").on("click", function () {
    $(".navbar-collapse.show").slideUp().removeClass("show");
  });
  $(".navbar-toggler").on("click", function () {
    $(".navbar-collapse").slideToggle().toggleClass("show");
  });
});
</script>

<style lang="scss" scoped>
.header {
  overflow: hidden;
  position: fixed;
  width: 100%;
  top: 0;
  z-index: 11;
  .nav {
    .logo {
      font-size: 24px;
      padding: 5px 20px;
    }
    .navbar-toggler {
      outline: none;
      border-radius: 10px;
      box-shadow: none;
      transition: 0.5s;
      .navbar-toggler-icon {
        display: flex;
        justify-content: center;
        align-items: center;
        font-size: 25px;
      }
    }
    .links {
      padding: 5px;
      .nav-item {
        .aaa {
          padding: 5px 20px;
          display: inline-block;
          font-size: 17px;
          text-decoration: none;
          border-radius: 15px;
          transform: scale(1);
          text-transform: uppercase;
          transition: all 0.5s ease-in-out;
          width: 100%;
          &::after {
            display: block;
            position: relative;
            left: 0;
            bottom: -3px;
            width: 0;
            height: 2px;
            content: "";
            transition: width 0.5s;
          }
          &.router-link-active {
            transform: scale(1.3);
            font-weight: bold;
            &::after {
              width: 100%;
            }
            @media (max-width: 767px) {
              margin-left: 60px;
            }
          }
          @media (min-width: 768px) and (max-width: 991px) {
            padding: 5px 10px;
            font-size: 14px;
          }
        }
        &.switch-theme-btn,
        &.switch-language-btn {
          padding: 0;
          cursor: pointer;
          display: flex;
          align-items: center;
          .aaa {
            font-size: 27px;
            @media (min-width: 768px) and (max-width: 991px) {
              font-size: 15px;
              &.switch-language-btn,
              &.switch-theme-btn {
                display: flex;
                align-items: center;
              }
            }
          }
        }
      }
      @media (min-width: 768px) and (max-width: 991px) {
        margin-right: 0;
      }
    }
  }
}
</style>
