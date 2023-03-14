<template>
  <div
    :class="[
      'recepter-search-field',
      {
        focused: isFocused,
        hovered: isHovered,
        flexible: !isExpanded,
        disabled,
      },
    ]"
  >
    <label class="search-input-wrapper">
      <input
        :value="modelValue"
        type="text"
        class="search__input"
        :placeholder="placeholder"
        :disabled="disabled"
        @focus="changeFocus(true)"
        @blur="changeFocus(false)"
        @mouseenter="changeHover(true)"
        @mouseleave="changeHover(false)"
        @input="changeValue"
      />

      <div class="search-icon-wrapper">
        <svg class="search__icon"
          width="24"
          height="24"
          viewBox="0 0 24 24"
          fill="none"
          xmlns="http://www.w3.org/2000/svg"
        >
          <path
            d="M10.1356 18.2712C14.6288 18.2712 18.2712 14.6288 18.2712 10.1356C18.2712 5.64243 14.6288 2 10.1356 2C5.64243 2 2 5.64243 2 10.1356C2 14.6288 5.64243 18.2712 10.1356 18.2712Z"
            stroke="#212121"
            stroke-linecap="round"
            stroke-linejoin="round"
          />
          <path
            d="M16.0679 16.0679L22.0001 22.0001"
            stroke="#212121"
            stroke-linecap="round"
            stroke-linejoin="round"
          />
        </svg>
      </div>
    </label>
  </div>
</template>

<script>
export default {
  name: "RecepterSearchField",
  props: {
    modelValue: {
      type: String,
      default: "",
    },
    expand: {
      type: Boolean,
      default: false,
    },
    disabled: {
      type: Boolean,
      default: false,
    },
    placeholder: {
      type: String,
      default: "",
    },
    flexible: {
      type: Boolean,
      default: false,
    },
  },
  data() {
    return {
      isFocused: false,
      isHovered: false,
    };
  },
  computed: {
    isExpanded() {
      if (!this.flexible) return false;

      return this.modelValue || this.isFocused;
    },
  },
  watch: {
    isExpanded(newValue) {
      this.$emit("expand:status", newValue);
    },
  },
  methods: {
    changeValue(event) {
      this.$emit("update:modelValue", event.target.value);
    },
    changeFocus(status) {
      this.isFocused = status;
    },
    changeHover(status) {
      this.isHovered = status;
    },
  },
};
</script>

<style lang="scss">
.recepter-search-field {
  display: flex;
  flex-direction: column;
  max-width: 340px;
  transition: 0.5s;

  &.hovered {
    .search__input {
      border: none;
      border: 1px solid $main;
    }
  }

  &.flexible {
    max-width: 56px;

    @include breakpoint (lg) {
      max-width: 46px;
    }

    .search__input {
      padding: 16px 20px 16px 26px;

      @include breakpoint(lg) {
        padding: 10px 20px 10px 26px;
      }

      @media screen and (max-width: 420px) {
        padding: 5px 15px 5px 5px;
      }
    }

    .search-icon-wrapper {
      left: 16px;
    }
  }

  &.focused {
    .search__input {
      border: 1px solid $stroke;
    }

    .search__icon {
      stroke: $stroke;
    }
  }

  &.disabled {
    .search-input-wrapper {
      background: $gray-100;
    }

    .search__input {
      border-color: $gray-100;
      color: $gray-300;
      cursor: not-allowed;

      &::placeholder {
        stroke: $gray-300;
      }
    }

    .search__icon {
      stroke: $gray-300;
    }
  }

  .search {
    &-input-wrapper {
      position: relative;
      display: flex;
      background: $white;
      border-radius: 34px;
    }

    &__input {
      width: 100%;
      color: $main;
      background-color: none;
      padding: 16px 20px 16px 70px;
      border: 1px solid #fff;
      border-radius: 34px;
      outline: none;
      transition: 0.5s;
      &::placeholder {
        color: $gray-350;
      }

      @include breakpoint(lg) {
        padding: 10px 20px 10px 50px;
      }

      @media screen and (max-width: 420px) {
        padding: 5px 15px 5px 45px;
      }
    }

    &-icon-wrapper {
      -right: 10px;
      position: absolute;
      left: 20px;
      top: 50%;
      width: 24px;
      height: 24px;
      transform: translateY(-50%);
      transition: 0.3s;
      pointer-events: none;

      @include breakpoint(lg) {
        width: 20px;
        height: 20px;
      }

    }

    &__icon {
      width: 100%;
      height: 100%;
      fill: none;
      stroke: $main;
    }
  }
}
</style>
