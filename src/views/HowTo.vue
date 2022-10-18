
<template>
  <div class="howTo">
    <div class="howToTitleContainer">
      <h2 class="howTo__title">{{title}}</h2>
    </div>
    <div class="howTo__grid">
      <HowToTemplate
        v-for="info in Infos"
        :howToNumber="info.id"
        :howToTitle="info.title"
        :howToText="info.text"
        :class="info.class"
        :isFirst="info.id === 1"
      />
    </div>
  </div>
</template>

<script>
import HowToTemplate from "../components/HowTo/HowToTemplate.vue";
import Infos from "../assets/data/Infos.json";
export default {
  name: "HowTo",
  components: {
    HowToTemplate,
  },

  data() {
    return {
      Infos,
      title: "Как принять участие?",
      isFirst: true,
    };
  },
}
</script>

<style lang="scss" scoped>
@import "../assets/styles/variables.scss";

.howTo {
  display: flex;
  flex-direction: column;
  margin: 0 auto;
  width: 1088px;
  gap: 28px;
  padding-bottom: 150px;

  &__title {
    @include txtTitle;
    margin-bottom: 40px;
  }

  &__grid {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 110px;
  }
}

@media screen and (max-width: 768px) {
  .howTo {
    width: 100%;
    margin-bottom: -80px;

    .howToTitleContainer {
      text-align: center;
      width: 100%;
      display: flex;
      justify-content: center;
      padding: 0 40px;
    }
    &__title {
      font-weight: 700;
      font-size: 30px;
      line-height: 36px;
    }
    &__grid {
      grid-template-columns: repeat(1, 1fr);
      gap: 40px;
    }
  }
}


</style>