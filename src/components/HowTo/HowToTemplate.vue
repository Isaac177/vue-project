<template>
  <div class="howTo__grid__box">
    <div class="howTo__grid__box__number">
      <h1>{{howToNumber}}</h1>
    </div>
    <div class="howTo__grid__box__text">
      <h3 class="howTo__grid__box__text__title">
        {{howToTitle}}
        <span v-if="isFirst" class="howTo__grid__box__text__title__link">
          <HowToLink text="заявку"/>
        </span>
      </h3>
      <p class="howTo__grid__box__text__description">{{howToText}}</p>
    </div>
  </div>
</template>

<script>
import HowToLink from "./HowToLink.vue";
export default {
  name: "HowToTemplate",

  components: {HowToLink},
  props: {
    howToNumber: {
      type: Number,
      required: true,
    },
    howToTitle: {
      type: String,
      required: true,
    },
    howToText: {
      type: String,
      required: true,
    },

    isFirst: {
      type: Boolean,
      required: true,
    },
  }
}
</script>

<style lang="scss" scoped>
@import "../../assets/styles/variables.scss";

.howTo__grid__box {
  display: flex;
  flex-direction: column;
  align-items: start;
  justify-content: start;
  width: 400px;
  height: auto;
  border-radius: 12px;
  text-align: center;

  &__number {
    display: flex;
    justify-content: center;
    align-items: center;
    border-radius: 16px;
    width: 62px;
    height: 62px;
    margin-bottom: 24px;
  }

  &__text {
    text-align: start;
    &__title {
      @include darkText;
      //font-weight: bold;
      margin-bottom: 12px;

      @media screen and (max-width: 768px) {
        font-weight: 500;
        font-size: 20px;
        line-height: 26px;
      }
    }

    &__description {
      @include smallText;

      @media screen and (max-width: 768px) {
        font-weight: 400;
        font-size: 18px;
        line-height: 24px;
        padding: 0 20px;
      }
    }

    @media (max-width: 768px) {
      text-align: center;
    }
  }

  &.first {
    & .howTo__grid__box__number {
      background: $secondary-blue-light;
      color: $secondary-blue;
    }

    @media (max-width: 768px) {
      align-items: center;

      & .howTo__grid__box__number {
       align-items: center;
      }
    }
  }

  &.second {
    & .howTo__grid__box__number {
      background: $secondary-purple;
      color: $primary-purple;
    }

    @media (max-width: 768px) {
      align-items: center;

      & .howTo__grid__box__number {
        align-items: center;
      }
    }
  }

  &.third {
    & .howTo__grid__box__number {
      background: $secondary-green;
      color: $primary-green;
    }

    @media (max-width: 768px) {
      align-items: center;

      & .howTo__grid__box__number {
        align-items: center;
      }
    }
  }

  &.fourth {
    & .howTo__grid__box__number {
      background: $secondary-yellow-light;
      color: $secondary-yellow;
    }

    @media (max-width: 768px) {
      align-items: center;

      & .howTo__grid__box__number {
        align-items: center;
      }
    }
  }

  @media screen and (max-width: 768px) {
    width: 100%;
    margin-bottom: 24px;
  }
}
</style>