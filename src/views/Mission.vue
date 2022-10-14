<script>
import MissionText from "../components/Mission/MissionText.vue";
import Text from "../assets/data/Text.json";
import YellowBtn from "../components/Buttons/YellowBtn.vue";
export default {
  name: "Mission",
  components: {YellowBtn, MissionText},

  data() {
    return {
      missionTitle: "Наша миссия",
      Text,
      btnLink: "https://docs.google.com/forms/d/e/1FAIpQLSfm_Yj07urIb_fF0mTRGZgl5DWt5lC2qYd4TngwXWMgMHiYMg/viewform?usp=sf_link",
      btnText: "Присоединиться",
    }
  }
}
</script>

<template>
  <div class="mission__container">
    <div class="mission__img">
      <img src="../assets/img/MissionImg.svg" alt="mission">
    </div>
    <div class="mission__text">
      <MissionText
          v-for="text in Text"
        :missionTitle="missionTitle"
        :missionFirstParagraph="text.firstP"
        :missionSecondParagraph="text.secondP"
        :missionThirdParagraph="text.thirdP"
      />
      <div class="mission__button">
        <YellowBtn>
          <a :href="btnLink" target="_blank" class="mission__btnTxt">{{btnText}}</a>
        </YellowBtn>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
@import "../assets/styles/variables.scss";

.mission__container {
  display: flex;
  flex-direction: row;
  width: 1088px;
  height: auto;
  margin: 0 auto;
  gap: 40px;

  &__img {
    width : 553.37px;
    height : 455.5px;
  }

}

.yellowBtn > a {
  text-decoration: none;
  font-weight: 600;
  font-size: 18px;
  line-height: 22px;
  background: none;
  color: #10083F;
}

@media screen and (max-width: 768px) {
  .mission__container {
    flex-direction: column-reverse;
    width: 100%;
    height: auto;
    margin: 0 auto;
    gap: 40px;
  }
  .mission__img > img{
    width: 333px;
    height: 274.11px;
    padding: 0 10px;
    margin-bottom: 54px;
  }
  .mission__button {
    display: flex;
    justify-content: center;
    align-items: center;
    margin-top: -120px;

    &:active {
      transform: scale(0.9);
    }
  }
}
</style>