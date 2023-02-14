<template>
  <span class="aaa" @click="switchTheme()">
    <span v-if="currentTheme === 'dark-theme'">
      <font-awesome-icon
        class=""
        :icon="{
          prefix: 'fas',
          iconName: 'sun',
        }"
      />
    </span>
    <span v-else>
      <font-awesome-icon class="" :icon="{ prefix: 'fas', iconName: 'moon' }" />
    </span>
  </span>
</template>
<script>
export default {
  name: "ThemeSwitcher",
  data() {
    return {
      currentTheme: localStorage.getItem("fk-theme-color") ?? "dark-theme",
    };
  },
  methods: {
    switchTheme() {
      if (this.currentTheme == "light-theme") {
        localStorage.setItem("fk-theme-color", "dark-theme");
        this.currentTheme = localStorage.getItem("fk-theme-color");
        this.$emit("switchTheme", "dark-theme");
      } else {
        localStorage.setItem("fk-theme-color", "light-theme");
        this.currentTheme = localStorage.getItem("fk-theme-color");
        this.$emit("switchTheme", "light-theme");
      }
    },
  },
};
</script>
<style lang="sass" scoped></style>
