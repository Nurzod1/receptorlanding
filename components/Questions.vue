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
            <g-button class="question-main__head-btn" text="ОБЩИЕ ВОПРОСЫ" />
            <g-button class="question-main__head-btn" text="МЕНЮ" />
            <g-button class="question-main__head-btn" text="ОПЛАТА" />
          </div>
          <div class="question-main__details">
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import GButton from "./GButton.vue";
import QuestionCard from "~/components/q_components/QuestionCard.vue";
export default {
  components: { GButton, QuestionCard },
  name: "Question",
};
</script>

<style lang="scss" scoped>
.question {
  padding-bottom: 89px;
  background-color: $gray-100;
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
    }

    &__title {
      font-family: Bitter;
      font-size: 36px;
      line-height: 130%;
    }
  }

  &-main {
    margin-left: 163px;
    &__head {
      display: flex;
      gap: 24px;

      &-btn {
      }
    }
  }
}
</style>