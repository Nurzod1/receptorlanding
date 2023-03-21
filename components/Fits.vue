<template>
  <div class="fits">
    <div class="fits-img">
      <img src="~/assets/images/FitsImg.png" alt="" />
    </div>
    <div class="container">
      <div class="fits-wrapper">
        <div class="fits-head">
          <div class="fits-head__line"></div>
          <div class="fits-head__title">Кому подходит?</div>
        </div>
        <VueSlickCarousel v-bind="settings" :arrows="true">
          <fits-card v-for="item in cardsrc" :key="item.number" :item="item" />
        </VueSlickCarousel>
      </div>
    </div>
  </div>
</template>

<script>
import VueSlickCarousel from "vue-slick-carousel";
import "vue-slick-carousel/dist/vue-slick-carousel.css";
// optional style for arrows & dots
import "vue-slick-carousel/dist/vue-slick-carousel-theme.css";
import FitsCard from "~/components/fits_components/FitsCard.vue";
export default {
  name: "Fits",
  components: { VueSlickCarousel, FitsCard },
  data() {
    return {
      settings: {
        arrows: true,
        focusOnSelect: true,
        infinite: false,
        speed: 500,
        slidesToShow: 1,
        slidesToScroll: 1,
        touchThreshold: 5,
        responsive: [
          {
            breakpoint: 768,
            settings: {
              slidesToShow: 1,
              slidesToScroll: 1,
              centerMode: true,
              centerPadding: "15px",
              arrows: false,
              dots: true,
            },
          },
          {
            breakpoint: 576,
            settings: {
              centerMode: true,
              centerPadding: "20px",
              arrows: false,
              dots: true,
            },
          },
          {
            breakpoint: 510,
            settings: {
              centerMode: true,
              centerPadding: "0px",
              arrows: false,
              dots: true,
            },
          },
        ],
      },
      cardsrc: [
        {
          firstimg: require("~/assets/images/FitsCardImg.jpg"),
          secondimg: require("~/assets/images/FitsCardImg1.jpg"),
          thirdimg: require("~/assets/images/FitsCardImg2.jpg"),
          number: "01",
          title: `Хозяйкам, уставшим от домашней рутины`,
          text: `Муж звонит с работы: «Дорогая, а что у нас на ужин? Я бы слона съел!»
          А у тебя как назло фантазия закончилась. Вроде умеешь и любишь 
          готовить, но все же не Гордон Рамзи, чтобы каждый день угощать 
          домашних кулинарными шедеврами… `,
          subtext: `«Рецептор» станет твоим личным шеф-поваром, под его руководством 
          вернешь вдохновение и будешь каждый день удивлять родных вкусной едой!`,
        },
        {
          firstimg: require("~/assets/images/FitsCardImg3.jpg"),
          secondimg: require("~/assets/images/FitsCardImg4.jpg"),
          thirdimg: require("~/assets/images/FitsCardImg5.jpg"),
          number: "02",
          title: `Заботливым мамам`,
          text: `Скоро придут со школы дети и нужно накормить их вкусным и полезным 
          обедом. Сама съела бы куриную грудку с салатом, но детей таким меню не обманешь. 
          Их нужно чем-то удивить, а иногда даже побаловать каким-нибудь десертом.`,
          subtext: `В нашем меню сотни рецептов, подходящих для детей разного возраста!`,
        },
        {
          firstimg: require("~/assets/images/FitsCardImg6.jpg"),
          secondimg: require("~/assets/images/FitsCardImg7.jpg"),
          thirdimg: require("~/assets/images/FitsCardImg8.jpg"),
          number: "03",
          title: `Людям, которые следят за здоровьем`,
          text: `Пицца, суши и гамбургеры – это, конечно вкусно, но все же разовая 
          история. Постоянно фастфудом питаться не будешь. А если будешь, то не 
          долго – пока здоровье не напомнит о себе.`,
          subtext: `С рецептами из нашего меню тебе не захочется возвращаться к быстрой еде!`,
        },
        {
          firstimg: require("~/assets/images/FitsCardImg9.jpg"),
          secondimg: require("~/assets/images/FitsCardImg10.jpg"),
          thirdimg: require("~/assets/images/FitsCardImg11.jpg"),
          number: "04",
          title: `Деловым женщинам`,
          text: `После рабочего дня так не хочется устраивать “вторую смену” и стоять еще час 
          у плиты. Хочется вместо этого почитать книгу, полежать в ванной, 
          сходить на маникюр или к косметологу. Или просто уделить больше времени семье.`,
          subtext: `Конструктор предложит интересные, вкусные и, главное, быстрые рецепты завтраков, 
          обедов и ужинов. И ты сможешь легко совмещать роли деловой женщины и умелой хозяйки!`,
        },
      ],
    };
  },
};
</script>

<style lang="scss">
.fits {
  background-color: $gray-100;
  padding: 80px 0;
  position: relative;

  @include breakpoint(lg) {
    padding: 60px 0;
  }

  @include breakpoint(md) {
    padding: 40px 0;
  }

  @include breakpoint(sm) {
    padding: 30px 0;
  }
  &-img {
    width: 483px;
    height: 354px;
    position: absolute;
    top: -8px;
    right: 10px;
    z-index: 20;

    @media screen and (max-width: 1335px) {
      width: 368px;
      height: 270px;
    }

    @include breakpoint(md) {
      width: 318px;
      height: 232px;
    }

    @media screen and (max-width: 870px) {
      width: 273px;
      height: 206px;
    }

    @include breakpoint(sm) {
      width: 186px;
      height: 137px;
    }

    @media screen and (max-width: 550px) {
      display: none;
    }

    img {
      width: 100%;
      height: 100%;
    }
  }

  &-wrapper {
  }

  &-head {
    display: flex;
    flex-direction: column;
    align-items: center;
    margin-bottom: 62px;

    @include breakpoint(xs) {
      margin-bottom: 20px;
    }

    &__line {
      width: 145px;
      height: 2px;
      border-bottom: 1px solid $black;
      margin-bottom: 65px;

      @include breakpoint(md) {
        margin-bottom: 40px;
      }

      @include breakpoint(sm) {
        margin-bottom: 30px;
        width: 125px;
      }

      @include breakpoint(xs) {
        margin-bottom: 20px;
      }
    }

    &__title {
      font-family: Bitter;
      font-size: 36px;
      font-weight: 500;
      line-height: 130%;
      z-index: 21;

      @include breakpoint(lg) {
        font-size: 32px;
      }

      @include breakpoint(md) {
        font-size: 30px;
      }

      @include breakpoint(sm) {
        font-size: 24px;
      }

      @media screen and (max-width: 350px) {
        font-size: 22px;
      }
    }
  }

  .slick {
    &-slide {
      @include breakpoint(sm) {
        max-width: 505px;
      }
    }
    &-slider {
      position: relative;
    }
    &-slider {
      max-width: 1170px;
    }

    &-arrow {
      min-width: 50px;
      min-height: 50px;
    }

    &-prev {
      left: 726px;
      top: 558px !important;
      z-index: 30;

      @include breakpoint(lg) {
        top: 498px !important;
        left: 625px;
      }

      @include breakpoint(md) {
        left: 435px;
        top: 344px !important;
      }

      &:before {
        content: url("./assets/icons/PrevArrow.svg");
        width: 50px;
        min-width: 50px;
        min-height: 50px;
        padding: 5px 11px 5px 9px;
        color: black;
        border: 1px solid #000;
        border-radius: 50%;
      }
    }

    &-next {
      right: 340px;
      top: 558px !important;
      z-index: 30;

      @include breakpoint(xl) {
        right: 310px;
      }

      @include breakpoint(lg) {
        right: 218px;
        top: 498px !important;
      }

      @include breakpoint(md) {
        right: 180px;
        top: 344px !important;
      }
      &:before {
        content: url("./assets/icons/NextArrow.svg");
        min-width: 50px;
        min-height: 50px;
        padding: 5px 9px 5px 11px;
        color: black;
        border: 1px solid #000;
        border-radius: 50%;
      }
    }
  }
}
</style>