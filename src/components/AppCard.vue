<template>
  <div class="text-center">
    <img class="mb-3" :src="item.image" alt="" />
    <h4>{{ item.name }}</h4>
    <div>
      <p>{{ item.origin }}</p>
    </div>
    <div>
      <p class="fw-bold">{{ item.species }}</p>
    </div>
  </div>
</template>

<script>
export default {
  name: "AppCard",
  props: {
    item: Object,
  },
};
</script>

<style lang="scss" scoped>
@import "../assets/styles/variables.scss";
h4 {
  text-transform: uppercase;
  &:after {
    content: "";
    display: block;
    width: 30%;
    height: 2px;
    margin: 1rem auto;
    background: currentColor;
  }
}
img {
  border-radius: 50%;
  box-shadow: 0 0 6px 3px rgba(#000, 0.15);
}
</style>