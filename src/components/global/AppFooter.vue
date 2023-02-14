<template>
  <div class="footer">
    <div class="container">
      <div class="row">
        <div class="col-6">
          <div
            :class="`footer-content-left ${
              $i18n.locale === 'ar' ? 'text-end' : 'text-start'
            }`"
          >
            {{ $t("footer.Developed With") }}
            <span class="love"
              ><font-awesome-icon
                class="skill-icons"
                :icon="{ prefix: 'fas', iconName: 'heart' }"
            /></span>
            {{ $t("footer.And") }}
            <img class="vue-image" src="../../assets/logo.png" alt="Vue" />
          </div>
        </div>
        <div class="col-6">
          <div
            :class="`footer-content-right ${
              $i18n.locale === 'ar' ? 'text-start' : 'text-end'
            }`"
          >
            &copy; 2022
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "AppFooter",
};
</script>

<style lang="scss" scoped>
.footer {
  position: relative;
  height: 50px;
  margin-top: 50px;
  display: flex;
  justify-content: center;
  align-items: center;
  .footer-content-left {
    .love {
      margin: 0 5px;
      font-size: 20px;
    }
    .vue-image {
      height: 20px;
      width: 20px;
      margin: 0 5px 3px;
    }
  }
}
</style>
