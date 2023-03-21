<template>
  <div class="navbar">
    <div class="container">
      <div class="navbar-wrapper">
        <div class="navbar-start">
          <burger-menu :value="value" @input="$emit('input', $event)" />
          <div class="navbar-logo">
            <img src="../assets/images/Logo.png" alt="" />
          </div>
        </div>
        <div class="navbar-menu">
          <ul class="navbar-menu__list">
            <li class="navbar-menu__list-link">О проекте</li>
            <li class="navbar-menu__list-link">Меню на неделю</li>
            <li class="navbar-menu__list-link">Кулинарная школа</li>
            <li class="navbar-menu__list-link">Рецепты</li>
          </ul>
        </div>
        <div class="navbar-body">
          <r-search-field
            v-model="search"
            class="navbar-body__search"
            flexible
            @expand:status="isExpanded = $event"
          />
          <div class="navbar-body__btn">
            <svg
              width="22"
              height="22"
              viewBox="0 0 22 22"
              fill="none"
              xmlns="http://www.w3.org/2000/svg"
            >
              <path
                d="M1 12.25L11 1L21 12.25M3.22222 13.5V18.5C3.22222 19.163 3.45635 19.7989 3.8731 20.2678C4.28984 20.7366 4.85507 21 5.44444 21H16.5556C17.1449 21 17.7102 20.7366 18.1269 20.2678C18.5437 19.7989 18.7778 19.163 18.7778 18.5V13.5"
                stroke="#212121"
                stroke-linecap="round"
                stroke-linejoin="round"
              />
            </svg>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import RSearchField from "~/components/navbar_components/RSearchField";
import BurgerMenu from "~/components/navbar_components/BurgerMenu.vue";
export default {
  name: "MainNavbar",
  components: { RSearchField, BurgerMenu },
  props: {
    value: {
      type: Boolean,
      required: true, 
    }
  },
  data() {
    return {
      search: ""
    }
  }
};
</script>

<style lang="scss">
.input {
  max-width: 915px;
}
.navbar {
  &-wrapper {
    display: flex;
    justify-content: space-between;
    align-items: center;
    height: 76px;

    @include breakpoint(sm) {
      height: 60px;
    }
  }

  &-start {
    display: flex;
    gap: 20px;
    align-items: center;

    @include breakpoint(sm) {
      gap: 10px;
    }
  }
  &-logo {
    width: 180px;
    height: 34px;
    margin-right: 150px;

    @include breakpoint(lg) {
      margin-right: 70px;
      width: 130px;
      height: 25px;
    }

    @media screen and (max-width: 400px){      
      width: 110px;
      height: 20px;
      margin-right: 20px;
    }

    img {
      width: 100%;
      height: 100%;
    }
  }

  &-menu {
    &__list {
      display: flex;
      gap: 21px;

      @include breakpoint(lg) {
        gap: 15px;
      }

      @include breakpoint(md) {
        display: none;
      }

      &-link {
        font-weight: 400;
        line-height: 19px;
        white-space: nowrap;
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

  &-body {
    display: flex;
    align-items: center;
    gap: 10px;

    @include breakpoint(lg) {
      gap: 10px;
    }

    &__btn {
      display: flex;
      align-items: center;
      justify-content: center;
      width: 35px;
      height: 25px;
      cursor: pointer;
      transition: all 0.3s;

      @include breakpoint(lg) {
        width: 20px;
        height: 20px;
      }
      svg {
        transition: 0.3s;
        path {
          transition: 0.3s;
        }
      }
      &:hover {
        svg {
          path {
            stroke: $stroke;
          }
        }
      }
    }
  }
}
</style>
