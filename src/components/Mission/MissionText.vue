<template>
<div class="missionText">
    <div class="missionText__title">
        <h2>{{missionTitle}}</h2>
    </div>
    <div class="missionText__text">
        <p>{{missionFirstParagraph}}</p>
        <p>{{missionSecondParagraph}}</p>
        <p>{{missionThirdParagraph}}</p>
    </div>
  </div>
</template>

<script>
export default {
  name: "MissionText",

  props: {
    missionTitle: {
      type: String,
      required: true
    },
    missionFirstParagraph: {
      type: String,
      required: true
    },
    missionSecondParagraph: {
      type: String,
      required: true
    },
    missionThirdParagraph: {
      type: String,
      required: true
    },
  }
}
</script>

<style lang="scss" scoped>
@import "../../assets/styles/variables.scss";

.missionText {
  height: auto;
  margin-bottom: 85px;

  &__title {
    margin-bottom: 40px;
    h2 {
      @include txtTitle;
    }
  }

  &__text {
    @include smallText;
    p {
      margin-bottom: 24px;
    }
  }
}

@media screen and (max-width: 768px) {
  .missionText {
    display: flex;
    justify-content: center;
    flex-direction: column;

    &__title {
      text-align: center;
      margin-bottom: 40px;
      font-weight: 700;
      font-size: 30px;
      line-height: 36px;
    }

    &__text {
      text-align: center;
      margin-bottom: 40px;
      padding: 0 20px;
    }
  }
}

</style>