<template v-scroll-animation>
  <div class="overview" id="overview">
    <h1 class="overview__title">{{ overviewTitle }}</h1>
    <p class="overview__text">{{overviewText}}</p>
  </div>

</template>

<script>
export default {
  name: "Overview",

  props: {
    overviewTitle: String,
    overviewText: String,
  },

}
</script>

<style lang="scss" scoped>
@import "../assets/styles/variables.scss";
.overview {
  width: 100%;
  max-width: 1088px;
  text-align: center;
  margin: 0 auto;
  padding-bottom: 110px;

  &__title {
    @include txtTitle;
    margin-bottom: 32px;
  }
  &__text {
    @include smallText;
    width: 680px;
    height: 72px;
    margin: 0 auto;
    word-break: break-word;
  }
}

@media screen and (max-width: 768px) {
  .overview {
    width: 100%;
    max-width: 100%;
    padding: 0 30px;

    &__title {
      font-weight: 700;
      font-size: 30px;
      line-height: 36px;
      word-break: break-word;
    }

    &__text {
      width: 100%;
      height: auto;
      margin-bottom: 32px;
    }
  }
}
</style>