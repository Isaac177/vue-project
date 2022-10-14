
<script>
import HeroCnt from "../components/Hero/HeroCnt.vue";
import Nav from "../components/Hero/Nav.vue";
export default {
  name: "Hero",
  components: {Nav, HeroCnt}
}
</script>

<template>
  <header class="header">
    <div class="headerContainer">
      <Nav />
      <HeroCnt />
    </div>
  </header>
</template>

<style lang="scss" scoped>
@import "../assets/styles/variables.scss";
.header {
  background: $tertiary-grey;
  height: 100vh;
  margin-bottom: 110px;

  @media screen and (max-width: 768px) {
    height: 100%;
    width: 100%;
  }
}
.headerContainer {
  width: 1088px;
  margin: 0 auto;

  @media screen and (max-width: 768px) {
    width: 100% !important;
  }
}
</style>