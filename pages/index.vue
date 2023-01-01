<template>
  <section class="container border p-5 mx-auto my-10">
    working ...
    <!-- <form
      class="space-y-10 flex flex-col text-slate-700 font-normal"
      @submit.prevent="login()"
    >
      <label for="">
        <span class="capitalize"> username </span>
        <input class="border rounded" type="text" v-model="form.user" />
      </label>

      <label for="">
        <span class="capitalize"> password </span>
        <input class="border rounded" type="text" v-model="form.password" />
      </label>

      <button
        class="p-2 w-36 rounded bg-slate-800 text-slate-100 font-semibold"
      >
        Submit
      </button>
    </form> -->
  </section>
</template>

<!-- <script>
export default {
  data() {
    return {
      form: {},
    };
  },

  methods: {
    login() {
      this.$axios.get("https://fakestoreapi.com/products").then((res) => {
        console.log(res);
      });
    },
  },
};
</script> -->

<script setup>
const data = await useAsyncData("count", () =>
  $fetch("https://fakestoreapi.com/products")
);

console.log("fetching=> ", data);
</script>
