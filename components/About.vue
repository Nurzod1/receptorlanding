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
            <div class="about-gallery__img">
              <img src="../assets/images/AboutImg.jpg" alt="" />
            </div>
            <div class="about-gallery__img">
              <img src="../assets/images/AboutImg1.jpg" alt="" />
            </div>
          </div>
          <div class="about-gallery__img">
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
  &-wrapper {
    display: flex;
    justify-content: space-between;
  }

  &-text {
    font-size: 18px;
    line-height: 130%;
    &__title {
      font-family: Bitter;
      font-size: 36px;
      line-height: 130%;
      margin-bottom: 40px;
    }

    &__wrapper {
      max-width: 386px;
      display: flex;
      flex-direction: column;
      justify-content: center;
    }
  }

  &-gallery {
    display: flex;
    gap: 30px;

    &__imgs {
      display: flex;
      flex-direction: column;
      gap: 26px;
    }
  }
}
</style>