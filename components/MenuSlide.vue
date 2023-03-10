<template>
  <div class="menu">
    <div class="container">
      <div class="menu-wrapper">
        <div class="menu-head">
          <div class="menu-head__line"></div>
          <div class="menu-head__title">Наше меню поможет вам:</div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "MenuSlide",
};
</script>

<style lang="scss" scoped>
.menu {
  padding: 85px 0;

  &-wrapper {
    display: flex;
    flex-direction: column;
    align-items: center;
  }
  &-head {
    display: flex;
    flex-direction: column;
    align-items: center;
    margin-bottom: 40px;

    &__line {
      width: 145px;
      height: 2px;
      border-bottom: 1px solid $black;
      margin-bottom: 65px;
    }

    &__title {
      font-family: Bitter;
      font-size: 36px;
      line-height: 130%;
    }
  }
}
</style>