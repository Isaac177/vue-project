
<template>
  <div class="card">
    <div class="card__img">
      <img :src="cardImg" alt="img">
    </div>
    <div class="card__text">
      <h3 class="card__title">{{ cardTitle }}</h3>
      <p class="card__description">{{ cardDescription }}</p>
    </div>
  </div>
</template>

<script>
export default {
  name: "Card",

  props: {
    cardTitle: {
      type: String,
      required: true
    },
    cardDescription: {
      type: String,
      required: true
    },
    cardImg: {
      type: String,
      required: true
    },
  }
}
</script>

<style lang="scss" scoped>
@import "../../assets/styles/variables.scss";

.card {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  width: 340px;
  height: 441px;
  border-radius: 12px;
  text-align: center;

  &__img {
    width: 150px;
    height: 150px;
    margin-bottom: 36px;
  }

  &__title {
    @include darkText;
    margin-bottom: 12px;
  }

  &__description {
    @include smallText;
    display: none;
  }

  &.firstCard,
  &.secondCard,
  &.thirdCard {
    border: none;
    padding: 0 24px;

    &:hover {
      animation: scale-size;
      animation-duration: 0.5s;
      transform: scale(1.1);
      cursor: pointer;
      box-shadow: 0 4px 16px rgba(0, 0, 0, 0.1);

      & .card__description {
        display: block;
        animation: ease-in;
        animation-duration: 1s;
        animation-name: text-in;
        transform: inherit;
        color: #78735E;

        @keyframes text-in {
          0% {
            opacity: 0;
          }
          50% {
            opacity: 0;
          }
          100% {
           opacity: 1;
          }
        }
      }

      & .card__img, .card__title{
        animation: ease-in;
        animation-duration: 0.5s;
        animation-name: img-up;
        transform: inherit;

        @keyframes img-up {
          0% {
            transform: translateY(50px);
          }
          100% {
            transform: translateY(0);
          }
        }
      }

      @keyframes scale-size {
        0% {
          transform: scale(1);
        }
        100% {
          transform: scale(1.1);
        }
      }
    }
  }

  &.firstCard {
    background: $primary-yellow-light
  }

  &.secondCard {
    background: $secondary-blue-light
  }

  &.thirdCard {
    background: $dark;

    & .card__title {
      color: #ffffff;
    }

    & .card__description {
      color: rgba(255, 255, 255, 0.8) !important;
    }
  }

  @media (max-width: 768px) {
    &.firstCard,
    &.secondCard,
    &.thirdCard {
      &.card__description {
        display: block;
      }
    }
  }
}

@media (max-width: 768px) {
  .card {
    width: 342px;
    height: 362px;
  }
  .card__description {
    display: block;
  }
}

</style>