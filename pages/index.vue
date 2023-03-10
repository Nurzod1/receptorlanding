<template>
  <div>
    <navbar />
    <main-header />
    <advantage />
    <about />
    <our-menu />
    <subscribe />
    <questions />
  </div>
</template>

<script>
import Navbar from "~/components/Navbar.vue";
import MainHeader from "~/components/MainHeader.vue";
import Advantage from "~/components/Advantage.vue"
import About from '~/components/About.vue';
import MenuSlide from '~/components/MenuSlide.vue';
import Subscribe from '~/components/Subscribe.vue';
import Questions from '~/components/Questions.vue';
export default {
  name: "HomePage",
  components: { Navbar, MainHeader, Advantage, About, MenuSlide, Subscribe, Questions },
};
</script>
