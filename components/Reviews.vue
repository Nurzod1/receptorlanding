<template>
  <div class="review">
    <div class="container">
      <div class="review-wrapper">
        <div class="menu-head">
          <div class="menu-head__line"></div>
          <div class="menu-head__title">Наше меню поможет вам:</div>
        </div>
        <VueSlickCarousel v-bind="settings" :arrows="true">
          <review-card v-for="item in cardsrc" :key="item.id" :post="item" />
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
import ReviewCard from "~/components/reviews_components/ReviewCard.vue";
export default {
  name: "MenuSlide",
  components: { VueSlickCarousel, ReviewCard },
  data() {
    return {
      settings: {
        dots: true,
        arrows: true,
        focusOnSelect: true,
        infinite: false,
        speed: 500,
        slidesToShow: 3,
        slidesToScroll: 1,
        touchThreshold: 5,
        responsive: [
          {
            breakpoint: 1199,
            settings: {
              slidesToShow: 2,
              slidesToScroll: 1,
            },
          },
          {
            breakpoint: 991,
            settings: {
              slidesToShow: 2,
              slidesToScroll: 1,
              arrows: false,
            },
          },
          {
            breakpoint: 575,
            settings: {
              slidesToShow: 1,
              slidesToScroll: 1,
              centerMode: true,
              centerPadding: "20px",
              arrows: false,
              infinite: true,
            },
          },
        ],
      },
      cardsrc: [
        {
          img: require("~/assets/images/ReviewCardImg.png"),
          name: "Мария",
          text: `Не могу сказать, что стою у плиты целыми днями, но присутствую. Идеи
          очень часто беру на сайте кулинарных рецептов Рецептор, который для
          меня заменил настольную книгу по кулинарии.`,
          date: "8.05.2022",
          id: 1,
        },
        {
          img: require("~/assets/images/ReviewCardImg1.png"),
          name: "Анна",
          text: `Если я не знаю, что приготовить или подзабыла рецепт, я всегда знаю куда 
          мне посмотреть. За столько времени посещения этого сайта, я уже помню в каком рецепте, 
          есть нюанс, который меня интересует.`,
          date: "10.05.2022",
          id: 2,
        },
        {
          img: require("~/assets/images/ReviewCardImg.png"),
          name: "Мария",
          text: `Не могу сказать, что стою у плиты целыми днями, но присутствую. Идеи
          очень часто беру на сайте кулинарных рецептов Рецептор, который для
          меня заменил настольную книгу по кулинарии.`,
          date: "8.05.2022",
          id: 3,
        },
        {
          img: require("~/assets/images/ReviewCardImg1.png"),
          name: "Анна",
          text: `Если я не знаю, что приготовить или подзабыла рецепт, я всегда знаю куда 
          мне посмотреть. За столько времени посещения этого сайта, я уже помню в каком рецепте, 
          есть нюанс, который меня интересует.`,
          date: "10.05.2022",
          id: 4,
        },
      ],
    };
  },
};
</script>

<style lang="scss">
.review {
  padding: 85px 0;

  @include breakpoint(md) {
    padding: 45px 0;
  }

  @include breakpoint(sm) {
    padding: 35px 0;
  }
  &-wrapper {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
  }
  .slick {
    &-slider {
      position: relative;
    }

    &-slide {
      display: flex !important;
      justify-content: center;
    }
    &-slider {
      max-width: 1230px;
      margin-bottom: 43px;

      @media screen and (max-width: 1335px) {
        max-width: 1055px;
      }

      @include breakpoint(lg) {
        max-width: 750px;
        min-height: 360px;
      }
      @include breakpoint(sm) {
        max-width: 550px;
        min-height: 360px;
      }

      @include breakpoint(xs) {
        max-width: 320px;
        margin-bottom: 10px;
      }
    }

    &-arrow {
      min-width: 50px;
      min-height: 50px;
    }

    &-dots {
      @include breakpoint(xs) {
        bottom: -10px;
      }
    }

    &-next {
      right: -50px;
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
    &-prev {
      left: -50px;
      &:before {
        content: url("./assets/icons/PrevArrow.svg");
        width: 50px;
        min-width: 50px;
        left: -50px;
        height: 50px;
        min-height: 50px;
        padding: 5px 11px 5px 9px;
        color: black;
        border: 1px solid #000;
        border-radius: 50%;
      }
    }
  }
}
</style>