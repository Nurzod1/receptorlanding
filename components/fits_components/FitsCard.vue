<template>
  <div class="fits-about-wrapper">
    <div class="fits-about-gallery">
      <div class="fits-about-gallery__img third">
        <img :src="item.firstimg" alt="" />
      </div>
      <div class="fits-about-gallery__imgs">
        <div class="fits-about-gallery__img first">
          <img :src="item.secondimg" alt="" />
        </div>
        <div class="fits-about-gallery__img second">
          <img :src="item.thirdimg" alt="" />
        </div>
      </div>
    </div>
    <div class="fits-about-text__wrapper">
      <p class="fits-about-text__num">{{ item.number }}</p>
      <p class="fits-about-text__title">
        {{ item.title }}
      </p>
      <div class="fits-about-text">
        <p>
          {{ item.text }}
        </p>
        <p>
          {{ item.subtext }}
        </p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "FitsCard",
  props: {
    item: {
      type: Object,
      required: true,
    },
  },
};
</script>

<style lang="scss" scoped>
.fits {
  &-about {
    &-wrapper {
      display: flex !important  ;
      gap: 62px;
      max-width: 1170px;

      @include breakpoint(lg) {
        gap: 40px;
      }

      @include breakpoint(md) {
        gap: 20px;
      }

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

      @include breakpoint(md) {
        font-size: 14px;
        line-height: 120%;
      }

      p {
        &:first-child {
          margin-bottom: 24px;

          @include breakpoint(lg) {
            margin-bottom: 15px;
          }

          @include breakpoint(md) {
            margin-bottom: 10px;
          }
        }
      }

      &__num {
        font-family: Bitter;
        font-size: 64px;
        line-height: 130%;
        margin-bottom: 32px;

        @include breakpoint(lg) {
          font-size: 56px;
          margin-bottom: 0;
        }

        @include breakpoint(md) {
          font-size: 50px;
        }
      }
      &__title {
        font-family: Bitter;
        font-size: 36px;
        line-height: 130%;
        font-weight: 500;
        margin-bottom: 32px;

        @include breakpoint(lg) {
          font-size: 30px;
          line-height: 105%;
          margin-bottom: 20px;
        }

        @include breakpoint(md) {
          font-size: 24px;
          margin-bottom: 15px;
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
        max-width: 458px;
        display: flex;
        flex-direction: column;

        @media screen and (max-width: 375px) {
          max-width: 300px;
        }
      }
    }

    &-gallery {
      display: flex;
      gap: 30px;
      width: fit-content;

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
}
</style>