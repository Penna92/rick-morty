<template>
  <section class="container d-flex flex-wrap gap-5 justify-content-center">
    <app-loader v-if="loading" />
    <!-- <div -->
    <!-- class="text-center" -->
    <!-- v-for="character in characterList" -->
    <!-- :key="character.id" -->
    <!-- > -->
    <!-- <app-card :item="character" /> -->
    <!-- id: {{ item.id }} - name: {{ item.name }} - status: {{ item.status }} -
      type: {{ item.type }} - species: {{ item.species }} - -->
    <!-- <img class="mb-3" :src="item.image" alt="" /> -->
    <!-- <h4>{{ item.name }}</h4> -->
    <!-- <hr class="w-50 mx-auto" /> -->
    <!-- <p>{{ item.origin }}</p> -->
    <!-- <p class="fw-bold">{{ item.species }}</p> -->
    <!-- - origin: {{ item.origin }} -->
    <!-- </div> -->
    <div class="row">
      <div
        v-for="character in characterList"
        :key="character.id"
        class="col-6 col-md-4 col-lg-3 my-3"
      >
        <app-card :item="character" />
      </div>
    </div>
    <app-footer v-if="!loading" :len="characterList.length" />
  </section>
</template>
    
<script>
import AppLoader from "./AppLoader.vue";
import axios from "axios";
import AppCard from "./AppCard.vue";
import AppFooter from "./AppFooter.vue";
export default {
  name: "MainGrid",
  components: {
    AppLoader,
    AppCard,
    AppFooter,
  },
  data() {
    return {
      characterList: [],
      apiPath: "https://api.sampleapis.com/rickandmorty/",
      loading: false,
    };
  },
  mounted() {
    this.loading = true;
    axios
      .get(this.apiPath + "characters")
      .then((res) => {
        // console.log(res);
        this.characterList = res.data;
        console.log(this.characterList);
        this.loading = false;
      })
      .catch((error) => {
        console.log(error);
        this.loading = false;
      });
  },
};
</script>

<style lang="scss" scoped>
</style>