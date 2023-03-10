<template>
  <div class="subscribe">
    <div class="container">
      <div class="subscribe-wrapper">
        <div class="subscribe-head">
          <p class="subscribe-head__title">Стоимость подписки</p>
          <div class="subscribe-head__tooltip">
            <div
              :class="['subscribe-head__tooltip-block', { active: isActive }]"
            >
              <p>
                После оплаты подписки ты получаешь доступ в личный кабинет на
                нашем сайте. Дальше необходимо настроить меню под индивидуальные
                потребности с помощью фильтров конструктора рецептов. Отмечай
                количество приемов пищи в день, количество порций,
                предпочтительное время приготовления еды. <br />
                <br />
                Также есть возможность выбрать меню согласно пищевым привычкам –
                есть рецепты для веганов, низкокалорийное меню и блюда для
                детей. По необходимости можно исключить из рациона отдельные
                продукты. <br /><br />
                Если домой внезапно нагрянули гости, можешь изменить меню в этот
                день, заново рассчитав необходимое количество порций. Или
                выбрать вручную блюда для званого ужина из нашей базы рецептов.
              </p>
            </div>
            <div class="subscribe-head__tooltip-icon" @click="showTooltip">
              <svg
                width="24"
                height="24"
                viewBox="0 0 24 24"
                fill="none"
                xmlns="http://www.w3.org/2000/svg"
              >
                <path
                  opacity="0.75"
                  d="M12 24C18.6274 24 24 18.6274 24 12C24 5.37258 18.6274 0 12 0C5.37258 0 0 5.37258 0 12C0 18.6274 5.37258 24 12 24Z"
                  fill="#636363"
                />
                <path
                  d="M12.916 10.7352L10.1679 11.0824L10.0695 11.542L10.6096 11.6424C10.9624 11.7271 11.032 11.8553 10.9552 12.2097L10.0695 16.4046C9.83674 17.4896 10.1955 18 11.0392 18C11.6932 18 12.4528 17.6952 12.7972 17.2767L12.9028 16.7735C12.6628 16.9864 12.3124 17.071 12.0796 17.071C11.7496 17.071 11.6296 16.8376 11.7148 16.4263L12.916 10.7352ZM13 8.20959C13 8.53039 12.8736 8.83806 12.6485 9.0649C12.4235 9.29174 12.1182 9.41918 11.8 9.41918C11.4817 9.41918 11.1765 9.29174 10.9514 9.0649C10.7264 8.83806 10.6 8.53039 10.6 8.20959C10.6 7.88879 10.7264 7.58112 10.9514 7.35428C11.1765 7.12744 11.4817 7 11.8 7C12.1182 7 12.4235 7.12744 12.6485 7.35428C12.8736 7.58112 13 7.88879 13 8.20959Z"
                  fill="white"
                />
              </svg>
            </div>
          </div>
        </div>
        <div class="subscribe-cards">
          <div class="subscribe-cards__item">
            <div class="subscribe-cards__item-about">
              <p class="subscribe-cards__item-about--time">1 месяц</p>
              <div class="subscribe-cards__item-about--line"></div>
              <p class="subscribe-cards__item-about--price">
                <span>1500</span> руб
              </p>
            </div>
            <div class="subscribe-cards__item-about--img">
              <img src="../assets/images/SubscribeImg.jpg" alt="" />
            </div>
            <g-button class="subscribe-btn" text="ВЫБРАТЬ" />
            <div class="subscribe-cards__item-img">
              <img src="../assets/images/ItemImg.png" alt="" />
            </div>
          </div>
          <div class="subscribe-cards__item">
            <div class="subscribe-cards__item-about">
              <p class="subscribe-cards__item-about--time">3 месяц</p>
              <div class="subscribe-cards__item-about--line"></div>
              <p class="subscribe-cards__item-about--price">
                <span>3500</span> руб
              </p>
            </div>
            <div class="subscribe-cards__item-about--img">
              <img src="../assets/images/SubscribeImg1.jpg" alt="" />
            </div>
            <g-button class="subscribe-btn" text="ВЫБРАТЬ" />
          </div>
          <div class="subscribe-cards__item">
            <div class="subscribe-cards__item-about">
              <p class="subscribe-cards__item-about--time">1 год</p>
              <div class="subscribe-cards__item-about--line"></div>
              <p class="subscribe-cards__item-about--price">
                <span>12000</span> руб
              </p>
            </div>
            <div class="subscribe-cards__item-about--img">
              <img src="../assets/images/SubscribeImg2.jpg" alt="" />
            </div>
            <g-button class="subscribe-btn" text="ВЫБРАТЬ" />
            <div class="subscribe-cards__item-img second">
              <img src="../assets/images/ItemImg1.png" alt="" />
            </div>
          </div>
        </div>
        <div class="subscribe-foot">
          <img src="../assets/images/SubscripeFoot.jpg" alt="" />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import GButton from "./GButton.vue";
export default {
  components: { GButton },
  name: "subscribe",
  data() {
    return {
      isActive: false,
    };
  },
  methods: {
    showTooltip() {
      this.isActive = !this.isActive;
    },
  },
};
</script>

<style lang="scss" scoped>
.subscribe {
  padding: 80px 0;
  background-color: $gray-100;

  &-head {
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 20px;
    margin-bottom: 100px;
    &__title {
      font-family: Bitter;
      font-size: 36px;
      line-height: 130%;
    }

    &__tooltip {
      position: relative;

      &-block {
        opacity: 0;
        position: absolute;
        left: -584px;
        top: -134%;
        max-width: 560px;
        background: $gray-750;
        padding: 20px 22px 25px 30px;
        transition: 0.3s;
        z-index: 10;
        pointer-events: none;

        &.active {
          opacity: 1;
        }
        p {
          font-family: Raleway;
          font-size: 14px;
          line-height: 20px;
          color: $white;
        }
        &::after {
          content: " ";
          position: absolute;
          top: 17%;
          left: 100%; /* To the right of the tooltip */
          margin-top: -18px;
          border-width: 18px;
          border-style: solid;
          border-color: transparent transparent transparent $gray-750;
          pointer-events: none;
        }
      }

      &-icon {
        cursor: pointer;
      }
    }
  }

  &-cards {
    display: flex;
    justify-content: space-between;
    margin-bottom: 100px;
    &__item {
      width: 350px;
      height: 350px;
      position: relative;

      &-about {
        position: absolute;
        top: -50px;
        left: 85px;
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        gap: 15px;
        background-color: $white;
        padding: 20px 40px 30px;
        max-width: 180px;
        max-height: 180px;
        text-align: center;
        z-index: 6;

        &--img {
          position: relative;
          z-index: 5;
        }
        &--time {
          font-family: Bitter;
          font-size: 24px;
          line-height: 29px;
        }

        &--line {
          width: 83px;
          border-bottom: 1px solid $main;
        }

        &--price {
          font-family: Bitter;
          font-size: 36px;
          line-height: 43px;

          span {
            font-weight: 600;
          }
        }
      }
      &-img {
        position: absolute;
        top: 261px;
        right: 64px;
        z-index: 1;

        &.second {
          top: -175px;
          left: 175px;
        }
      }
    }
  }

  &-btn {
    position: absolute;
    top: 327px;
    left: 113px;
    padding: 12px 20px;
    border-radius: 100px;
    background-color: $white;
    color: $black;
    border: none;
    z-index: 6;
  }

  &-foot {
    width: 100%;
    height: 400px;

    img {
      width: 100%;
      height: 100%;
    }
  }
}
</style>