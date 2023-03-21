<template>
  <div class="menu">
    <div class="container">
      <div class="menu-wrapper">
        <div class="menu-head">
          <div class="menu-head__line"></div>
          <div class="menu-head__title">Наше меню поможет вам:</div>
        </div>
        <VueSlickCarousel v-bind="settings" :arrows="true">
          <menu-slide-card
            v-for="item in cardsrc"
            :key="item.id"
            :post="item"
          />
        </VueSlickCarousel>
        <g-button text="ПОДОБРАТЬ МЕНЮ" />
      </div>
    </div>
  </div>
</template>

<script>
import VueSlickCarousel from "vue-slick-carousel";
import "vue-slick-carousel/dist/vue-slick-carousel.css";
// optional style for arrows & dots
import "vue-slick-carousel/dist/vue-slick-carousel-theme.css";
import MenuSlideCard from "./menu_slide_components/MenuSlideCard.vue";
import GButton from "./GButton.vue";
export default {
  name: "MenuSlide",
  components: { VueSlickCarousel, MenuSlideCard, GButton },
  data() {
    return {
      cardsrc: [
        {
          img: require("~/assets/images/SlideCardImg1.jpg"),
          title: "ВЕРНУТЬ ВДОХНОВЕНИЕ",
          text:
            `Устал от домашней рутины, а есть что-то нужно каждый день. 
            Вроде умеешь и любишь готовить, но все же не Гордон Рамзи, 
            чтобы каждый день выдавать шедевры…  “Рецептор” вернет 
            вдохновение, будешь каждый день удивлять родных вкусной едой!`,
          id: 1,
        },
        {
          img: require("~/assets/images/SlideCardImg2.jpg"),
          title: "СЭКОНОМИТЬ ВРЕМЯ",
          text:
            `После рабочего дня так не хочется устраивать вторую смену на кухне. 
            Полежать с книгой, или прогуляться лишний раз – гораздо приятнее. 
            Совмещение делового человека и хозяйки на кухне возможно. “Рецептор” 
            каждую неделю выдает готовое меню со списком продуктов. И тебе больше 
            не придется вручную искать и записывать рецепты, вести списки продуктов 
            и подсчитывать калории.`,
          id: 2,
        },
        {
          img: require("~/assets/images/SlideCardImg3.jpg"),
          title: "ПОДОБРАТЬ ПИТАНИЕ",
          text:
            `Следишь за фигурой и подсчитываешь калории? Потому что понимаешь пицца, 
            суши и бургеры – это, конечно вкусно, но все же разовая история. 
            Здоровье быстро напомнит о себе. В пару кликов настраиваешь диету, 
            сложность, частоту и количество приемов пищи.`,
          id: 3,
        },
        {
          img: require("~/assets/images/SlideCardImg4.jpg"),
          title: "СЭКОНОМИТЬ ДЕНЬГИ",
          text: `С конструктором меню больше не придется ходить в магазин за продуктами 
          каждый день – можно купить все необходимое сразу. А это значит, 
          что больше не будет импульсивных покупок.`,
          id: 4,
        },
        {
          img: require("~/assets/images/SlideCardImg5.jpg"),
          title: "ГОТОВИТЬ ЛЮБИМЫЕ БЛЮДА",
          text: `Ребенок не любит тыкву или у него аллергия на орехи? 
          Ты самостоятельно настраиваешь свое меню, подбирая продукты, 
          подходящие всем членам семьи - убирая из рациона в любой момент. 
          У нас сотни рецептов, для детей разного возраста!`,
          id: 5,
        },
        {
          img: require("~/assets/images/SlideCardImg6.jpg"),
          title: "СЭКОНОМИТЬ ВРЕМЯ НА МАГАЗИН",
          text: `Подобрав меню, конструктор предложит список продуктов на неделю, 
          которые необходимо купить. Можно сделать это самостоятельно либо заказать 
          продукты в одном из магазинов прямо у нас на сайте. 
          Для этого достаточно перейти по ссылке и оплатить заказ.`,
          id: 6,
        },
      ],
      settings: {
        dots: true,
        arrows: true,
        focusOnSelect: true,
        infinite: false,
        speed: 500,
        slidesToShow: 4,
        slidesToScroll: 1,
        touchThreshold: 5,
        responsive: [
          {
            breakpoint: 1335,
            settings: {
              slidesToShow: 3,
              slidesToScroll: 1,
            },
          },
          {
            breakpoint: 1045,
            settings: {
              slidesToShow: 2,
              slidesToScroll: 1,
              centerMode: true,
              centerPadding: "20px",
              arrows: false,
              infinite: true,
            },
          },
          {
            breakpoint: 800,
            settings: {
              slidesToShow: 2,
              slidesToScroll: 1,
              centerMode: true,
              centerPadding: "20px",
              arrows: false,
              infinite: true,
            },
          },
          {
            breakpoint: 541,
            settings: {
              slidesToShow: 1,
              slidesToScroll: 1,
              centerMode: true,
              centerPadding: "20px",
              arrows: false,
              infinite: true,
            },
          },
          {
            breakpoint: 350,
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
    };
  },
};
</script>

<style lang="scss">
.menu {
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
    &-slider {
      position: relative;
    }
    &-slider {
      max-width: 1230px;
      min-height: 470px;
      margin-bottom: 43px;

      @media screen and (max-width: 1335px) {
        max-width: 930px;
      }

      @media screen and (max-width: 1045px) {
        max-width: 700px;
        min-height: 360px;
      }

      @media screen and (max-width: 800px) {
        max-width: 460px;
      }
      @media screen and (max-width: 540px) {
        max-width: 250px;
      }
    }

    &-arrow {
      min-width: 50px;
      min-height: 50px;
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