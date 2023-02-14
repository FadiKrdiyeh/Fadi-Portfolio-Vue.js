<template>
  <div
    :class="`
    ${currentTheme} ${$i18n.locale === 'ar' ? 'arabic-locale' : ''}`"
    :dir="$i18n.locale === 'en' ? 'ltr' : 'rtl'"
  >
    <app-header class="header-container" @switchTheme="updateTheme" />
    <div class="container page-content">
      <router-view />
    </div>
    <app-footer />
  </div>
</template>

<script>
import AppHeader from "@/components/global/AppHeader.vue";
import AppFooter from "@/components/global/AppFooter.vue";
export default {
  name: "App",
  components: {
    AppHeader,
    AppFooter,
  },
  data() {
    return {
      currentTheme: localStorage.getItem("fk-theme-color") ?? "dark-theme",
    };
  },
  methods: {
    updateTheme() {
      this.currentTheme =
        localStorage.getItem("fk-theme-color") ?? "dark-theme";
    },
  },
};

// var $ = require("jquery");
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
.page-content {
  min-height: calc(100vh - 200px);
}
</style>
