<template>
  <div class="accordion"><slot /></div>
</template>

<script>
export default {
  name: "Accordion",
  data() {
    return {
      Accordion: {
        count: 0,
        active: null,
      },
    };
  },
  provide() {
    return { Accordion: this.Accordion };
  },
};
</script>

<style lang="scss" scoped>

</style>