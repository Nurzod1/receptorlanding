<template>
  <div class="menu">
    <div class="container">
      <div class="menu-wrapper">
        <div class="menu-head">
          <div class="menu-head__line"></div>
          <p class="menu-head__title">Тебе точно сюда, если:</p>
        </div>
        <div class="menu-main">
          <div class="menu-main__items">
            <div class="menu-main__items-wrapper">
              <div class="menu-main__items-card">
                <div class="menu-main__items-card--img">
                  <img src="../assets/images/MenuImg.png" alt="" />
                </div>
                <p class="menu-main__items-card--text">
                  Хочешь вернуть контроль на кухне, а не быть ее заложником.
                </p>
              </div>
              <div class="menu-main__items-card">
                <div class="menu-main__items-card--img">
                  <img src="../assets/images/MenuImg1.png" alt="" />
                </div>
                <p class="menu-main__items-card--text">
                  Хочешь готовить вкусно и разнообразно, но не планируешь
                  становиться шеф-поваром.
                </p>
              </div>
              <div class="menu-main__items-card">
                <div class="menu-main__items-card--img">
                  <img src="../assets/images/MenuImg.png" alt="" />
                </div>
                <p class="menu-main__items-card--text">
                  Хочешь иметь несколько часов в день на себя.
                </p>
              </div>
            </div>
            <div class="menu-main__items-wrapper">
              <div class="menu-main__items-card">
                <div class="menu-main__items-card--img">
                  <img src="../assets/images/MenuImg2.png" alt="" />
                </div>
                <p class="menu-main__items-card--text">
                  Хочешь олучать удовольствие от процесса приготовления еды.
                </p>
              </div>
              <div class="menu-main__items-card">
                <div class="menu-main__items-card--img">
                  <img src="../assets/images/MenuImg.png" alt="" />
                </div>
                <p class="menu-main__items-card--text">
                  Хочешь кормить родных полезной домашней едой.
                </p>
              </div>
              <div class="menu-main__items-card">
                <div class="menu-main__items-card--img">
                  <img src="../assets/images/MenuImg.png" alt="" />
                </div>
                <p class="menu-main__items-card--text">
                  Хочешь иметь несколько часов в день на себя
                </p>
              </div>
            </div>
          </div>
          <g-button class="white" text="ПОДОБРАТЬ МЕНЮ" />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import GButton from "./GButton.vue";
export default {
  components: { GButton },
  name: "OurMenu",
};
</script>
<style lang="scss" scoped>
.menu {
  display: flex;
  align-items: center;
  min-height: 100vh;
  background: url(../assets/images/MenuBackground.jpg);
  background-size: cover;
  color: $white;
  padding: 20px;

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
      height: 1px;
      border-bottom: 2px solid $white;
      margin-bottom: 65px;

      @include breakpoint(md) {
        margin-bottom: 40px;
      }

      @include breakpoint(sm) {
        margin-bottom: 30px;
        width: 125px;
      }
    }

    &__title {
      font-family: Bitter;
      font-size: 36px;
      line-height: 130%;

      @include breakpoint(lg) {
        font-size: 32px;
      }

      @include breakpoint(md) {
        font-size: 30px;
      }

      @include breakpoint(sm) {
        font-size: 24px;
      }

      @media screen and (max-width:340px) {
        font-size: 22px;
      }
    }
  }

  &-main {
    display: flex;
    flex-direction: column;
    align-items: center;
    &__items {
      display: flex;
      gap: 240px;
      justify-content: center;
      margin-bottom: 32px;

      @include breakpoint(lg) {
        gap: 150px;
      }

      @include breakpoint(md) {
        gap: 30px;
      }

      @include breakpoint(sm) {
        flex-direction: column;
      }

      @media screen and (max-width: 450px) {
        gap: 15px;
      }

      &-wrapper {
        display: flex;
        flex-direction: column;
        gap: 50px;
        justify-content: space-between;

        @include breakpoint(md) {
          gap: 30px;
        }

        @media screen and (max-width: 450px) {
          gap: 15px;
        }
      }

      &-card {
        display: flex;
        gap: 25px;
        align-items: center;

        @include breakpoint(md) {
          gap: 15px;
        }

        &--text {
          font-size: 18px;
          line-height: 130%;
          max-width: 250px;

          @include breakpoint(sm) {
            font-size: 14px;
          }

          @media screen and (max-width: 400px) {
            max-width: 170px;
          }
        }

        &--img {
          width: 71px;
          height: 71px;

          @include breakpoint(md) {
            width: 60px;
            height: 60px;
          }

          img {
            width: 100%;
            height: 100%;
          }
        }
      }
    }
  }
}
</style>