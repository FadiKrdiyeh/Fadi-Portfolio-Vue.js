<template>
  <span class="aaa">
    <span v-if="$i18n.locale === 'en'" @click="updateLanguage('ar')">
      <font-awesome-icon :icon="{ prefix: 'fas', iconName: 'language' }" />
      AR
    </span>
    <span v-else-if="$i18n.locale === 'ar'" @click="updateLanguage('en')">
      <font-awesome-icon :icon="{ prefix: 'fas', iconName: 'language' }" />
      EN
    </span>
  </span>
</template>
<script>
export default {
  name: "LocaleSwitcher",
  data() {
    return {
      locales: ["en", "ar"],
    };
  },
  methods: {
    updateLanguage(l) {
      this.$i18n.locale = l;
      localStorage.setItem("fk-locale-lang", l);
    },
  },
  mounted() {
    if (localStorage.getItem("fk-locale-lang")) {
      this.$i18n.locale = localStorage.getItem("fk-locale-lang");
    } else {
      localStorage.setItem("fk-locale-lang", this.$i18n.locale);
    }
  },
};
</script>
<style lang="sass" scoped></style>
