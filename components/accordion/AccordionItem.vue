<template>
  <div class="accordion__item">
    <div class="accordion__head">
      <div
        class="accordion__trigger"
        :class="{ accordion__trigger_active: visible }"
        v-html="title"
      ></div>
      <div :class="['accordion__button', { active: visible }]" @click="open">
        <svg
          width="11"
          height="8"
          viewBox="0 0 11 8"
          fill="none"
          xmlns="http://www.w3.org/2000/svg"
        >
          <path
            d="M9.05102 1.72437L5.5 5.27539L1.94897 1.72437"
            stroke="#333333"
            stroke-width="2.5"
            stroke-miterlimit="10"
            stroke-linecap="round"
          />
        </svg>
      </div>
    </div>
    <transition
      name="accordion"
      @enter="start"
      @after-enter="end"
      @before-leave="start"
      @after-leave="end"
    >
      <div class="accordion__wrapper" v-show="visible">
        <div class="accordion__content"><slot /></div>
      </div>
    </transition>
  </div>
</template>

<script>
export default {
  name: "AccordionItem",
  props: ["title"],
  inject: ["Accordion"],
  data() {
    return {
      index: null,
    };
  },
  computed: {
    visible() {
      return this.index == this.Accordion.active;
    },
  },
  methods: {
    open() {
      if (this.visible) {
        this.Accordion.active = null;
      } else {
        this.Accordion.active = this.index;
      }
    },
    start(el) {
      el.style.height = el.scrollHeight + "px";
    },
    end(el) {
      el.style.height = "";
    },
  },
  created() {
    this.index = this.Accordion.count++;
  },
};
</script>

<style lang="scss" scoped>
.accordion-enter-active, .accordion-leave-active {
  will-change: height, opacity;
  transition: height 0.3s ease; 
  overflow: hidden;
  }
.accordion-enter, .accordion-leave-to {
  height: 0 !important;
  opacity: 0;

} 
.accordion {
  &__trigger {
    border-radius: 10px;
    background-color: $white;
    color: $black;
    max-width: 800px;
    font-weight: 500;
    font-size: 18px;
    line-height: 130%;

    @include breakpoint(xs) {
      font-size: 16px;
    }
  }
  &__head {
    display: flex;
    justify-content: space-between;
  }
  &__content {
    font-size: 16px;
    line-height: 110%;
    margin-top: 9px;

    @include breakpoint(xs) {
      font-size: 14px;
    }
  }
  &__item {
    background-color: $white;
    border-radius: 10px;
    margin-bottom: 16px;
    max-width: 950px;
    transition: 0.3s;
    padding: 15px 20px;

    @include breakpoint(xs) {
      padding: 10px 15px;
    }
  }
  &__wrapper {
  }

  &__button {
    width: 30px;
    height: 30px;
    min-width: 30px;
    min-height: 30px;
    border-radius: 50%;
    border: 1.5px solid $gray-150;
    display: flex;
    justify-content: center;
    align-items: center;
    transition: 0.3s;
    cursor: pointer;

    &.active {
      transform: rotate(180deg);
    }
  }
}
</style>