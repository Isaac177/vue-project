
<template>
  <Hero
    :title="title"
    :btnText="btnText"
    :btnLink="btnLink"
  />
  <Overview
    :overviewTitle="overviewTitle"
    :overviewText="overviewText"
  />
  <Features />
  <HowTo />
  <Mission />

</template>

<script>
import Hero from "./views/Hero.vue";
import HowTo from "./views/HowTo.vue";
import Overview from "./views/Overview.vue";
import Features from "./views/Features.vue";
import Mission from "./views/Mission.vue";

export default {
  name: 'App',
  components: {
    Features,
    Overview,
    Hero, HowTo, Mission,
  },

  data() {
    return {
      title: "Стать нашим респондентом",
      btnText: "Я готов!",
      btnLink: "https://docs.google.com/forms/d/e/1FAIpQLSfm_Yj07urIb_fF0mTRGZgl5DWt5lC2qYd4TngwXWMgMHiYMg/viewform?usp=sf_link",
      overviewTitle: "Кто такой респондент?",
      overviewText: "Респондент - человек, принимающий участие в опросе, интервью или тестировании дизайна. Мы используем твои ответы в проектировании новых продуктов, чтобы сделать их понятнее, удобнее и приятнее для пользователей."
    };
  },
}

</script>

<style scoped>

</style>
