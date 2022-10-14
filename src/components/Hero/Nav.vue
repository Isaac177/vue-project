
<script>

export default {
  name: "Nav",

  data(){
    return {
      isToggleOpen: false,
    }
  },
  methods: {
    toggleMobile() {
      this.isToggleOpen = !this.isToggleOpen;
    }
  }

}
</script>
<!--Routes maybe removed-->
<template>
  <nav class="navBar">
    <div class="logo">
      <RouterLink to="/">
        <img src="../../assets/img/appLogo.svg" alt="logo" />
      </RouterLink>
    </div>

    <div class="navLinks">
      <ul>
        <li>
          <RouterLink to="/">Какие плюсы?</RouterLink>
        </li>
        <li>
          <RouterLink to="/features">Что потребуется от тебя</RouterLink>
        </li>
        <li>
          <RouterLink to="/howTo">Что потребуется от тебя</RouterLink>
        </li>
        <li>
          <RouterLink to="/mission">Наша миссия</RouterLink>
        </li>
        <li>
          <RouterLink to="/contacts">Присоединиться</RouterLink>
        </li>
      </ul>
    </div>

    <div class="toggle" @click="toggleMobile" v-if="isToggleOpen">
      <img src="../../assets/img/toggleClose.svg" alt="toggle" />
    </div>

    <div class="toggle" @click="toggleMobile" v-else>
      <img src="../../assets/img/toggle.svg" alt="toggle" />
    </div>

  </nav>

  <div class="mobileNav" v-if="isToggleOpen">
    <ul>
      <li>
        <RouterLink to="/">Какие плюсы?</RouterLink>
      </li>
      <li>
        <RouterLink to="/features">Что потребуется от тебя</RouterLink>
      </li>
      <li>
        <RouterLink to="/howTo">Что потребуется от тебя</RouterLink>
      </li>
      <li>
        <RouterLink to="/mission">Наша миссия</RouterLink>
      </li>
    </ul>
  </div>
</template>


<style lang="scss" scoped>
@import "../../assets/styles/variables.scss";
  .navBar {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 0 20px;
    height: 80px;

    @media (max-width: 768px) {
      height: 100%;
    }
  }

  .logo {
    width: 41px;
    height: 41px;
    display: flex;
    justify-content: center;
    align-items: center;

    @media (max-width: 768px) {
      margin: 28px 0 20px 0;
    }
  }

  .navLinks {
    ul {
      display: flex;
      justify-content: space-between;
      align-items: center;
      list-style: none;
      padding: 0;
      margin: 0;
      gap: 36px;

      li {
        a {
          @include navLinks;
          text-decoration: none;
        }
        &:hover {
          transition: background-position 0.5s ease;
          background: linear-gradient(90deg, #FFC700 0%, #FFC700 100%) 100%;
          background-size: 200%;
          color: #fff;
          -webkit-background-clip: text;
          -webkit-text-fill-color: transparent;
        }
      }
      &.mobile {
        display: none;
      }
    }

    @media (max-width: 768px) {
      ul {
        display: none;
        &.mobile {
          display: flex;
          flex-direction: column;
          justify-content: center;
          align-items: center;
          height: 100vh;
          width: 100%;
          background: #fff;
          position: absolute;
          top: 0;
          left: 0;
          z-index: 1;
          li {
            margin: 0 0 40px 0;
            a {
              font-size: 24px;
              line-height: 32px;
            }
          }
        }
      }
    }
  }

  .toggle {
    display: none;

    @media (max-width: 768px) {
      display: block;
      cursor: pointer;
    }
  }

  @media (max-width: 768px) {
    .mobileNav {
      background: $tertiary-grey;
      backdrop-filter: blur(10px);
      -webkit-backdrop-filter: blur(10px);
      border-radius: 10px;

      ul {
        display: flex;
        flex-direction: column;
        text-decoration: none;
        list-style: none;
        justify-content: center;
        align-items: center;
        height: 100vh;
        width: 100%;
        background: #fff;
        position: absolute;
        top: 0;
        left: 0;
        z-index: 1;
        li {
          margin: 0 0 40px 0;
          a {
            font-weight: 700;
            font-size: 24px;
            line-height: 32px;
            color: #10083F;
            text-decoration: none;
          }
        }
      }
    }
  }
</style>