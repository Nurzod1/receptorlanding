<template>
  <div class="btn">{{ text }}</div>
</template>

<script>
export default {
  name: "GButton",
  props: {
    text: String,
  },
};
</script>

<style lang="scss" scoped>
.btn {
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 16px 32px;
  border: 1px solid $main;
  border-radius: 40px;
  transition: .3s;
  cursor: pointer;


  @include breakpoint(md) {
    padding: 14px 22px;
    font-size: 14px;
  }

  @include breakpoint(xs) {
    padding: 7px 15px;
    font-size: 14px;
  }

  @media screen and (max-width: 365px){
    padding: 6px 10px;
    font-size: 12px;
  }

  &:hover {
    background-color: $gray-100;
  }

  &.dark {
    background-color: $main;
    color: $white;
    transition: .5s;
    cursor: pointer;

    &:hover {
      background-color: $gray-700;
      border-color: $gray-700;
    }
  }

  &.white {
    border: 1px solid $white;
    color: $white;

    &:hover {
      background-color: $white;
      color: $main;
    }
  }
}
</style>