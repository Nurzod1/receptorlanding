<template>
  <div class="header">
    <div class="container">
      <div class="header-wrapper">
        <div class="header-about">
          <div class="header-about__title">
            <p>
              Конструктор рецептов — <br />
              настрой своё меню на неделю в пару кликов!
            </p>
          </div>
          <div class="header-about__subtitle">
            <p>
              Рецептор подберёт индивидуальный план питания для вашей семьи и
              сэкономит силы на приготовления еды.
            </p>
          </div>
          <g-button class="dark" text="МЕНЮ НА НЕДЕЛЮ"/>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import GButton from './GButton.vue';
export default {
  components: { GButton },
  name: "main-header",
};
</script>

<style lang="scss" scoped>
.header {
  background: url("~/assets/images/HeaderBg.png");
  min-height: 100vh;
  background-size: cover;

  &-wrapper {
    display: flex;
    justify-content: center;
  }

  &-about {
    display: flex;
    flex-direction: column;
    align-items: center;
    text-align: center;
    gap: 16px;
    margin-top: 80px;

    &__title {
      font-family: Bitter;
      font-size: 36px;
      line-height: 130%;
      max-width: 781px;
    }

    &__subtitle {
      font-size: 24px;
      line-height: 130%;
      max-width: 515px;
      margin-bottom: 8px;
    }

    &__btn {
      width: 236px;
      height: 57px;
      background: $main;
      border-radius: 40px;
      color: $white;
      transition: 0.3s;

      &:hover {
        background: $gray-700;
      }
    }
  }
}
</style>
