<template>
  <div class="features">
    <div class="titleContainer">
      <h2 class="features__title">{{ cardBigTitle }}</h2>
    </div>

    <div class="features__cards" >
      <Card
        v-for="card in Cards"
        :class="card.cardClass"
        :cardImg="card.cardImg"
        :cardTitle="card.cardTitle"
        :cardDescription="card.cardDescription"
      />
    </div>

  </div>
</template>

<script>
import Card from "../components/HowTo/Card.vue";
import Cards from "../assets/data/Cards.json";
export default {
  name: "Features",
  components: {
    Card,
  },

  data() {
    return {
      Cards,
      cardBigTitle: "Какие плюсы?",
    };
  },
}
</script>

<style lang="scss" scoped>
@import "../assets/styles/variables.scss";

.features {
  display: flex;
  flex-direction: column;
  margin: 0 auto;
  width: 1088px;
  gap: 28px;
  padding-bottom: 110px;

  &__title {
    @include txtTitle;
    margin-bottom: 32px;
  }

  &__cards {
    display: flex;
    flex-direction: row;
    align-items: center;
    justify-content: space-between;
    gap: 28px;
  }
}

.titleContainer {
  display: flex;
  justify-content: start;
  width: 1088px;
  padding: 0 40px 0 0;
}

@media screen and (max-width: 768px) {
  .features {
    width: 100%;
    padding: 0 40px 0 40px;
    text-align: center;

    &__title {
      text-align: center;
      font-weight: 700;
      font-size: 30px;
      line-height: 36px;
      margin-bottom: 24px;
    }

    &__cards {
      flex-direction: column;
      align-items: center;
      justify-content: center;
      margin-bottom: 80px;
    }

    .titleContainer {
      display: flex;
      justify-content: center;
      text-align: center;
    }
  }

  .titleContainer {
    width: 100%;
    padding: 0;
  }
}
</style>