<template>
  <div :class="['sidebar', { active: active }]">
    <div class="sidebar-menu__list">
      <button class="sidebar-exit" @click="active = !active">
        <svg
          width="24"
          height="24"
          viewBox="0 0 24 24"
          fill="none"
          xmlns="http://www.w3.org/2000/svg"
        >
          <path
            d="M11.9997 21.1666C17.0623 21.1666 21.1663 17.0625 21.1663 11.9999C21.1663 6.93728 17.0623 2.83322 11.9997 2.83322C6.93706 2.83322 2.83301 6.93728 2.83301 11.9999C2.83301 17.0625 6.93706 21.1666 11.9997 21.1666Z"
            stroke="#212121"
            stroke-linecap="round"
            stroke-linejoin="round"
          />
          <path
            d="M14.75 9.25L9.25 14.75"
            stroke="#212121"
            stroke-linecap="round"
            stroke-linejoin="round"
          />
          <path
            d="M9.25 9.25L14.75 14.75"
            stroke="#212121"
            stroke-linecap="round"
            stroke-linejoin="round"
          />
        </svg>
      </button>
      <ul class="sidebar-menu__list">
        <li class="sidebar-menu__list-link">О проекте</li>
        <li class="sidebar-menu__list-link">Меню на неделю</li>
        <li class="sidebar-menu__list-link">Кулинарная школа</li>
        <li class="sidebar-menu__list-link">Рецепты</li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: "MainSidebar",
  props: {
    active: {
      type: Boolean,
      default: false,
    },
  },
};
</script>

<style lang="scss">
.sidebar {
  flex: 1;
  align-items: center;
  justify-content: center;
  width: 310px;
  position: fixed;
  top: 0;
  left: 0;
  bottom: 0;
  background: $main;
  transition: 0.3s ease;
  margin-left: -310px;
  color: $white;

  @include breakpoint(sm) {
    width: 290px;
    margin-left: -290px;
  }

  @include breakpoint(xs) {
    width: 190px;
    margin-left: -190px;
  }

  &.active {
    margin-left: 0px;
  }

  &-menu {
    &__list {
      margin-top: 100px;
      margin-left: 20px;
      &-link {
        font-weight: 400;
        line-height: 19px;
        white-space: nowrap;
        margin-bottom: 10px;
        transition: 0.3s;
        cursor: pointer;

        &:hover {
          color: $stroke;
        }

        @include breakpoint(lg) {
          font-size: 14px;
        }
      }
    }
  }

  &-exit {
    position: absolute;
    top: 30px;
    right: 20px;

    svg {
      path {
        stroke: $white;
      }
    }

  }
}
</style>
