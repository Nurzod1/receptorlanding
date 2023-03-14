<template>
  <div class="question">
    <div class="container">
      <div class="question-wrapper">
        <div class="question-head">
          <div class="question-head__line"></div>
          <p class="question-head__title">Часто задаваемые вопросы</p>
        </div>
        <div class="question-main">
          <div class="question-main__head">
            <g-button
              :class="activeButton === item.id ? 'active' : ''"
              class="question-main__head-btn"
              v-for="item in button"
              :key="item.id"
              :text="item.text"
              @click.native="activeButton = item.id"
            />
          </div>
          <div class="question-main__accordion">
            <accordion>
              <accordion-item
                title="Что, если мне будет сложно придерживаться меню? Например, 
сегодня не захочется готовить суп, а завтра вдруг решу заказать пиццу…"
                ><div>
                  Вы настраиваете конструктор рецептов таким образом, что
                  приготовление еды не займет много времени. С помощью фильтра
                  можно выбрать блюда, приготовление которых займет не более
                  15-30 минут. Кроме того, заранее закупив продукты на неделю,
                  вам не придется тратить дополнительное время на походы в
                  магазин.
                </div></accordion-item
              >
              <accordion-item
                title="А что если я не справлюсь с темпом и не сумею себя организовать?"
                ><div>
                  Вы настраиваете конструктор рецептов таким образом, что
                  приготовление еды не займет много времени. С помощью фильтра
                  можно выбрать блюда, приготовление которых займет не более
                  15-30 минут. Кроме того, заранее закупив продукты на неделю,
                  вам не придется тратить дополнительное время на походы в
                  магазин.
                </div></accordion-item
              >
              <accordion-item
                title="Зачем платить за подписку, не проще поискать готовое меню в интернете?"
                ><div>
                  Вы настраиваете конструктор рецептов таким образом, что
                  приготовление еды не займет много времени. С помощью фильтра
                  можно выбрать блюда, приготовление которых займет не более
                  15-30 минут. Кроме того, заранее закупив продукты на неделю,
                  вам не придется тратить дополнительное время на походы в
                  магазин.
                </div></accordion-item
              >
              <accordion-item
                title="В меню не будет экзотических продуктов, которые не найти в обычном магазине?"
                ><div>
                  Вы настраиваете конструктор рецептов таким образом, что
                  приготовление еды не займет много времени. С помощью фильтра
                  можно выбрать блюда, приготовление которых займет не более
                  15-30 минут. Кроме того, заранее закупив продукты на неделю,
                  вам не придется тратить дополнительное время на походы в
                  магазин.
                </div></accordion-item
              >
            </accordion>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import GButton from "./GButton.vue";
import QuestionCard from "~/components/q_components/QuestionCard.vue";
import Accordion from "./accordion/Accordion.vue";
export default {
  components: { GButton, QuestionCard, Accordion },
  name: "Question",
  data() {
    return {
      activeButton: 1,
      button: [
        {
          text: "ОБЩИЕ ВОПРОСЫ",
          id: 1,
        },
        {
          text: "МЕНЮ",
          id: 2,
        },
        {
          text: "ОПЛАТА",
          id: 3,
        },
      ],
    };
  },
  methods: {
    test() {
      console.log("test");
    },
  },
};
</script>

<style lang="scss" scoped>
.question {
  padding-bottom: 80px;
  background-color: $gray-100;

  @include breakpoint(md) {
    padding-bottom: 60px;
  }

  @include breakpoint(sm) {
    padding-bottom: 40px;
  }

  @include breakpoint(xs) {
    padding-bottom: 20px;
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
    margin-bottom: 34px;

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
    &__head {
      display: flex;
      gap: 24px;
      margin-bottom: 30px;

      @include breakpoint(sm) {
        gap: 10px;
      }

      @include breakpoint(xs) {
        gap: 5px;
      }

      &-btn {
        &:hover {
          background-color: $gray-150;
        }

        &.active {
          background-color: $main;
          color: $white;
        }
      }
    }
  }
}
</style>