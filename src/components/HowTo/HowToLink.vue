
<script>
export default {
  name: "HowToLink",

  props: {
    text: {
      type: String,
      required: true
    }
  }
}
</script>

<template>
  <span class="howToLink">
    <a
        href="https://docs.google.com/forms/d/e/1FAIpQLSfm_Yj07urIb_fF0mTRGZgl5DWt5lC2qYd4TngwXWMgMHiYMg/viewform?usp=sf_link" target="_blank"
        style="color: #0C4DCE"
    >
      {{text}}
    </a>
  </span>
</template>

<style scoped>

</style>