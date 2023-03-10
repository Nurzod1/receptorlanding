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
            <g-button text="ПОПРОБОВАТЬ БЕСПЛАТНО" />
            <g-button class="dark" text="УЗНАТЬ ПОДРОБНЕЕ" />
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import GButton from './GButton.vue';
export default {
  components: { GButton },
  name: "Advantage"
};
</script>

<style lang="scss" scoped>
.advantage {
  margin: 65px 0;
  
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
      border-bottom: 2px solid $black;
      margin-bottom: 65px;
    }

    &__title {
      font-family: Bitter;
      font-size: 36px;
      line-height: 130%;
    }
  }

  &-main {
    &__items {
      display: flex;
      justify-content: center;
      max-width: 1017px;
      gap: 80px;
      margin-bottom: 33px;

      &-card {
        display: flex;
        flex-direction: column;
        align-items: center;
        max-width: 181px;
        
        &--img {
          width: 71px;
          height: 71px;
          margin-bottom: 24px;
          
          img {
            width: 100%;
            height: 100%;
          }
        }

        &--text {
          font-size: 18px;
          line-height: 130%;
          text-align: center;
        }
      }
    }

    &__buttons {
      display: flex;
      justify-content: center;
      gap: 50px;
    }
  }
}
</style>