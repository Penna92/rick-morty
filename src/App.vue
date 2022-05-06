<template>
  <div id="app">
    <HeaderComponent :title="titolo" />
    <main>
      <main-grid />
    </main>
  </div>
</template>

<script>
import HeaderComponent from "./components/HeaderComponent.vue";
import MainGrid from "./components/MainGrid.vue";

export default {
  name: "App",
  components: {
    HeaderComponent,
    MainGrid,
  },
  data() {
    return {
      titolo: "Rick and Morty",
    };
  },
};
</script>

<style lang="scss">
@import "./assets/styles/general.scss";
</style>
