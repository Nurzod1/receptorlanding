<template>
  <div class="menu">
    <div class="container">
      <div class="menu-wrapper">
        <div class="menu-head">
          <div class="menu-head__line"></div>
          <div class="menu-head__title">Наше меню поможет вам:</div>
        </div>
        <VueSlickCarousel :arrows="true" :dots="true">
          <div>Lorem ipsum dolor sit amet consectetur adipisicing elit. Odit, distinctio veritatis corrupti animi dolorem nisi veniam amet inventore ratione pariatur expedita, voluptate tempora quis reiciendis architecto nostrum, non voluptatibus. Quisquam!</div>
          <div>Lorem ipsum dolor, sit amet consectetur adipisicing elit. Exercitationem, doloremque eaque labore nam ullam earum in eum debitis ex, nisi dolores magni explicabo enim minus quasi tempora omnis odio molestiae!</div>
          <div>Lorem ipsum dolor, sit amet consectetur adipisicing elit. Exercitationem, doloremque eaque labore nam ullam earum in eum debitis ex, nisi dolores magni explicabo enim minus quasi tempora omnis odio molestiae!3</div>
          <div>Lorem ipsum dolor, sit amet consectetur adipisicing elit. Exercitationem, doloremque eaque labore nam ullam earum in eum debitis ex, nisi dolores magni explicabo enim minus quasi tempora omnis odio molestiae!4</div>
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
export default {
  name: "MenuSlide",
  components: { VueSlickCarousel },
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