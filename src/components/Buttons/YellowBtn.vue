
<template>
  <button class="yellowBtn">
    <slot></slot>
  </button>
</template>

<script>
export default {
  name: "YellowBtn"
}
</script>

<style lang="scss" scoped>
@import "../../assets/styles/variables.scss";
  .yellowBtn {
    justify-content: center;
    align-items: center;
    padding: 0 32px;
    cursor: pointer;
    width: fit-content;
    height: 56px;
    border-radius: 12px;
    border: 1px solid $primary-yellow;
    background: $primary-yellow;

    &:hover {
        background-color: $secondary-yellow;
      }

    &:active {
        transform: scale(1);
      }
  }
</style>