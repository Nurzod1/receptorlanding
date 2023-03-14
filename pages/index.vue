<template>
  <div>
    <main-navbar v-model="isSidebarOpen"/>
    <main-sidebar :active="isSidebarOpen"/>
    <main-header />
    <advantage />
    <menu-slide />
    <about />
    <our-menu />
    <subscribe />
    <questions />
    <main-footer />
  </div>
</template>

<script>
import MainNavbar from "~/components/MainNavbar.vue";
import MainHeader from "~/components/MainHeader.vue";
import Advantage from "~/components/Advantage.vue";
import About from "~/components/About.vue";
import MenuSlide from "~/components/MenuSlide.vue";
import Subscribe from "~/components/Subscribe.vue";
import Questions from "~/components/Questions.vue";
import MainFooter from "~/components/MainFooter.vue";
import MainSidebar from "../components/navbar/MainSidebar.vue";
export default {
  name: "HomePage",
  components: {
    MainNavbar,
    MainHeader,
    Advantage,
    About,
    MenuSlide,
    Subscribe,
    Questions,
    MainFooter,
    MainSidebar,
  },
  data() {
    return {
      isSidebarOpen: false,
    }
  }
};
</script>
