<template>
  <div class="about">
    <div class="container">
      <div class="about-wrapper">
        <div class="about-text__wrapper">
          <div class="about-text__title">
            «Рецептор» спасет от рутины на кухне!
          </div>
          <div class="about-text">
            Наш конструктор рецептов сэкономит время на походы по магазинам и
            приготовление еды без ущерба качеству. Оформив подписку на наш сайт,
            ты получишь разнообразное и сбалансированное питание каждый день.
          </div>
        </div>
        <div class="about-gallery">
          <div class="about-gallery__imgs">
            <div class="about-gallery__img first">
              <img src="../assets/images/AboutImg.jpg" alt="" />
            </div>
            <div class="about-gallery__img second">
              <img src="../assets/images/AboutImg1.jpg" alt="" />
            </div>
          </div>
          <div class="about-gallery__img third">
            <img src="../assets/images/AboutImg2.jpg" alt="" />
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "About",
};
</script>

<style lang="scss" scoped>
.about {
  background: $gray-100;
  padding: 80px 0;

  @include breakpoint(md) {
    padding: 60px 0;
  }

  @include breakpoint(sm) {
    padding: 40px 0;
  }

  @include breakpoint(xs) {
    padding: 20px 0;
  }

  &-wrapper {
    display: flex;
    justify-content: space-between;

    @include breakpoint(sm) {
      flex-direction: column;
      gap: 30px;
      align-items: center;
    }
  }

  &-text {
    font-size: 18px;
    line-height: 130%;

    @include breakpoint(lg) {
      font-size: 16px;
    }

    @include breakpoint(lg) {
      font-size: 14px;
    }

    &__title {
      font-family: Bitter;
      font-size: 36px;
      line-height: 130%;
      font-weight: 500;
      margin-bottom: 40px;

      @include breakpoint(lg) {
        font-size: 30px;
        margin-bottom: 30px;
      }

      @include breakpoint(md) {
        font-size: 24px;
      }

      @include breakpoint(sm) {
        font-size: 20px;
        margin-bottom: 20px;
      }

      @include breakpoint(xs) {
        font-size: 18px;
        margin-bottom: 10px;
      }

      @media screen and (max-width: 400px) {
        font-size: 16px;
      }
    }

    &__wrapper {
      max-width: 386px;
      display: flex;
      flex-direction: column;
      justify-content: center;

      @include breakpoint(lg) {
        max-width: 310px;
      }
    }
  }

  &-gallery {
    display: flex;
    gap: 30px;

    @include breakpoint(lg) {
      gap: 20px;
    }

    @include breakpoint(md) {
      gap: 10px;
    }

    &__imgs {
      display: flex;
      flex-direction: column;
      gap: 30px;

      @include breakpoint(lg) {
        gap: 20px;
      }

      @include breakpoint(md) {
        gap: 10px;
      }
    }

    &__img {
      &.first {
        width: 253px;
        height: 234px;

        @include breakpoint(lg) {
          width: 223px;
          height: 204px;
        }

        @include breakpoint(md) {
          width: 163px;
          height: 144px;
        }

        @media screen and (max-width: 470px) {
          width: 113px;
          height: 100px;
        }
      }

      &.second {
        width: 253px;
        height: 310px;

        @include breakpoint(lg) {
          width: 223px;
          height: 290px;
        }

        @include breakpoint(md) {
          width: 163px;
          height: 205px;
        }

        @media screen and (max-width: 470px) {
          width: 113px;
          height: 130px;
        }
      }

      &.third {
        width: 390px;
        height: 574px;

        @include breakpoint(lg) {
          width: 350px;
          height: 514px;
        }

        @include breakpoint(md) {
          width: 250px;
          height: 359px;
        }

        @media screen and (max-width: 470px) {
          width: 170px;
          height: 240px;
        }
      }

      img {
        width: 100%;
        height: 100%;
      }
    }
  }
}
</style>