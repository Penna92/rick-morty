<template>
  <footer>
    <div class="text-center">Found {{ len }} characters</div>
  </footer>
</template>

<script>
export default {
  name: "AppFooter",
  props: {
    len: Number,
  },
};
</script>

<style lang="scss" scoped>
</style>