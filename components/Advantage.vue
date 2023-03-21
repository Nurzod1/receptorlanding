<template>
  <div class="advantage">
    <div class="container">
      <div class="advantage-wrapper">
        <div class="advantage-head">
          <div class="advantage-head__line"></div>
          <div class="advantage-head__title">Преимущество</div>
        </div>
        <div class="advantage-main">
          <div class="advantage-main__items">
            <div class="advantage-main__items-card">
              <div class="advantage-main__items-card--img">
                <img src="../assets/images/cardimg.png" alt="" />
              </div>
              <div class="advantage-main__items-card--text">
                с подсчетом калорий
              </div>
            </div>
            <div class="advantage-main__items-card">
              <div class="advantage-main__items-card--img">
                <img src="../assets/images/cardimg1.png" alt="" />
              </div>
              <div class="advantage-main__items-card--text">
                с экономией 40 часов в неделю
              </div>
            </div>
            <div class="advantage-main__items-card">
              <div class="advantage-main__items-card--img">
                <img src="../assets/images/cardimg2.png" alt="" />
              </div>
              <div class="advantage-main__items-card--text">
                с учетом диеты и вкусов
              </div>
            </div>
            <div class="advantage-main__items-card">
              <div class="advantage-main__items-card--img">
                <img src="../assets/images/cardimg3.png" alt="" />
              </div>
              <div class="advantage-main__items-card--text">
                с экономией до 30% расходов на покупку продуктов!
              </div>
            </div>
            <div class="advantage-main__items-card">
              <div class="advantage-main__items-card--img">
                <img src="../assets/images/cardimg4.png" alt="" />
              </div>
              <div class="advantage-main__items-card--text">
                на любой кошелек
              </div>
            </div>
          </div>
          <div class="advantage-main__buttons">
            <g-button
              class="advantage-main__button"
              text="ПОПРОБОВАТЬ БЕСПЛАТНО"
            />
            <g-button
              class="advantage-main__button dark"
              text="УЗНАТЬ ПОДРОБНЕЕ"
            />
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import GButton from "./GButton.vue";
export default {
  components: { GButton },
  name: "Advantage",
};
</script>

<style lang="scss" scoped>
.advantage {
  margin: 65px 0;

  @include breakpoint(md) {
    margin: 45px 0;
  }

  @include breakpoint(sm) {
    margin: 35px 0;
  }

  @include breakpoint(xs) {
    margin: 20px 0;
  }

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

    @include breakpoint(xs) {
      margin-bottom: 20px;
    }

    &__line {
      width: 145px;
      height: 1px;
      border-bottom: 2px solid $black;
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
      font-weight: 500;

      @include breakpoint(lg) {
        font-size: 32px;
      }

      @include breakpoint(md) {
        font-size: 30px;
      }

      @include breakpoint(sm) {
        font-size: 24px;
      }
    }
  }

  &-main {
    &__items {
      display: flex;
      justify-content: center;
      max-width: 1017px;
      gap: 80px;
      margin-bottom: 33px;

      @include breakpoint(lg) {
        gap: 60px;
      }

      @include breakpoint(md) {
        display: grid;
        justify-items: center;
        grid-template-columns: 1fr 1fr 1fr 1fr;
        gap: 20px;
      }

      @include breakpoint(sm) {
        grid-template-columns: 1fr 1fr 1fr;
        gap: 15px;
      }

      @include breakpoint(xs) {
        grid-template-columns: 1fr 1fr;
      }

      @media screen and (max-width: 400px) {
        // grid-template-columns: 1fr;
      }

      &-card {
        display: flex;
        flex-direction: column;
        align-items: center;
        max-width: 181px;

        &--img {
          width: 71px;
          height: 71px;
          margin-bottom: 24px;

          @media screen and (max-width: 400px) {
            width: 60px;
            height: 60px;
            margin-bottom: 18px;
          }

          img {
            width: 100%;
            height: 100%;
          }
        }

        &--text {
          font-size: 18px;
          line-height: 130%;
          text-align: center;


          @include breakpoint(xs) {
            font-size: 16px;
          }
        }
      }
    }

    &__buttons {
      display: flex;
      justify-content: center;
      gap: 50px;

      @media screen and (max-width: 520px) {
        flex-direction: column;
        align-items: center;
        gap: 20px;
      }
    }

    &__button {
      @media screen and (max-width: 520px) {
        width: 70%;
      }
    }
  }
}
</style>