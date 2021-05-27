<template>
  <div class="tob-bar">
    <div class="container">
      <a href="#" style="color: inherit"><b-icon-twitter></b-icon-twitter></a>
      <a href="#" style="color: inherit"><img src="@/assets/whatsapp-16.png" /></a>
      <button class="languages">
        <span>اللغة العربية</span>
        <b-icon-caret-down-fill class="pt-1 mx-2"></b-icon-caret-down-fill>
      </button>
    </div>
  </div>
</template>

<script>
export default {
  name: "TobBar",
};
</script>

<style lang="scss" scoped>
.tob-bar {
  padding: 10px 0;
  background: #0d2e75;
  .container {
    display: flex;
    justify-content: flex-end;
    align-items: center;
    color: #fff;
    > * {
      margin: 0 10px;
    }
    .languages {
      background: transparent;
      border: none;
      outline: none;
      color: #fff;
    }
  }
}
</style>