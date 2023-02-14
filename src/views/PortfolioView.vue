<template>
  <div class="portfolio">
    <div class="title">
      {{ $t("portfolio.Sorry, There Is No Hosted Projects Except This Now") }}
    </div>
  </div>
</template>
<script>
export default {
  name: "PortfolioView",
};
</script>
<style lang="scss" scoped>
.portfolio {
  padding-top: 100px;
  .title {
    font-size: 30px;
  }
}
</style>
