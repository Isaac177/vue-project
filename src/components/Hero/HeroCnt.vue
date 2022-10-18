
<template>
    <div class="heroCnt">
      <div class="heroCnt__left">
        <h1>{{title}}</h1>
        <p>
          Мы хотим услышать твое мнение, опыт
          и боли общения с цифровыми продуктами Beeline.
        </p>
        <YellowBtn>
          <a :href="btnLink" class="btnTxt">{{btnText}}</a>
        </YellowBtn>
      </div>
      <div class="heroCnt__right">
        <img :src="heroImg" alt="heroImg" />
      </div>
    </div>
</template>

<script>
import Nav from "./Nav.vue";
import HeroImg from '../../assets/img/HeroImg.svg';
import YellowBtn from "../Buttons/YellowBtn.vue";
export default {
  name: "Hero",
  components: {YellowBtn, Nav, HeroImg},
  props: {
    title: {
      type: String,
      default: "Стать нашим респондентом",
    },
    btnText: {
      type: String,
      default: "Я готов!",
    },
    btnLink: {
      type: String,
      default: "https://docs.google.com/forms/d/e/1FAIpQLSfm_Yj07urIb_fF0mTRGZgl5DWt5lC2qYd4TngwXWMgMHiYMg/viewform?usp=sf_link",
    },
    heroImg: {
      type: String,
      default: HeroImg,
    },
  },
}
</script>

<style lang="scss" scoped>
@import "../../assets/styles/variables.scss";
  .heroCnt {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 0 20px;
    height: 80vh;

    .heroCnt__left {
      width: 50%;
      h1 {
        @include txtTitle;
        margin-bottom: 24px;
      }
      p {
        @include smallText;
        margin-bottom: 24px;
      }
      .btn {
        width: 300px;
        height: 60px;
        border-radius: 10px;
        border: none;
        font-size: 24px;
        line-height: 32px;
        font-weight: 500;
        cursor: pointer;
      }
    }
    .heroCnt__right {
      width: 50%;
      img {
        width: 647.73px;
        height: 429px;
      }
    }

    @media screen and (max-width: 768px) {
      flex-direction: column;
      height: auto;
      .heroCnt__left {
        width: 100%;
        text-align: center;
        h1 {
          margin: 50px 0 26px 0;
          font-weight: 700;
          font-size: 30px;
          line-height: 36px;
        }
        p {
          margin-bottom: 36px;
        }
        .btn {
          width: 158px;
          height: 48px;
          font-weight: 600;
          font-size: 16px;
          line-height: 20px;

          &:hover {
            background-color: $primary-yellow;
            color: #ffffff;
          }

          &:active {
            background-color: $primary-yellow;
            color: #ffffff;
          }
        }
      }
      .heroCnt__right {
        width: 100%;
        img {
          width: 353.57px;
          height: 234.18px;
          margin-top: 60px;
        }
      }
    }
  }

.btnTxt {
  font-weight: 600;
  font-size: 18px;
  line-height: 22px;
  color: $primary-blue;
  text-decoration: none;
}
</style>