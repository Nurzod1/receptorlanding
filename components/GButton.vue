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

  &.dark {
    width: 247px;
    height: 56px;
    background-color: $main;
    color: $white;
  }

  &.white {
    width: 234px;
    height: 52px;
    border: 1px solid $white;
    color: $white;
  }
}
</style>