<template>
  <section class="p-3 bg-white border-l-4 border-[#62A48E]" :style="{ height }">
    <h6 class="text-[#62A48E] font-semibold text-sm">Simple item</h6>
    <p class="text-[10px]">Simple Location</p>
  </section>
</template>

<script>
export default {
  props: {
    height: {
      default: "auto",
    },
    event: {
      default: {},
    },
  },
};
</script>

<style></style>
