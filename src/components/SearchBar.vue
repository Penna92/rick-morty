<template>
  <div>
    <div class="input-group">
      <!-- <input
        type="text"
        class="form-control"
        placeholder="Recipient's username"
        aria-label="Recipient's username with two button addons"
        v-model="inputText"
        @keyup.enter="search"
      />
      <button
        class="btn btn-outline-secondary"
        type="button"
        @click.prevent="$emit('search', inputText)"
      >
        Search
      </button>
      <button
        class="btn btn-outline-secondary"
        type="button"
        @click.prevent="reset"
      >
        Reset
      </button> -->
      <select name="genre" id="genre" v-model="inputText" @change="search">
        <option value="">All</option>
        <option
          :value="specie"
          v-for="specie in characterSpecies"
          :key="specie"
        >
          {{ specie }}
        </option>
      </select>
    </div>
  </div>
</template>

<script>
export default {
  name: "SearchBar",
  data() {
    return {
      inputText: "",
    };
  },
  props: ["characterSpecies"],
  methods: {
    search() {
      this.$emit("search", this.inputText);
      //   this.inputText = "";
    },
    reset() {
      this.inputText = "";
      this.$emit("search", this.inputText);
    },
  },
};
</script>

<style>
</style>