<template>
  <div>
    <div class="body" v-for="item in all" :key="item.id">
      <h1>{{ item.id }}. {{ item.name }}</h1>
      <h4>{{ item.email }}</h4>
    </div>
  </div>
</template>

<style>
.body {
  text-align: center;
}
</style>

<script>
export default {
  data() {
    return {
      all: [],
    };
  },
  methods: {
    async getData() {
      const res = await this.$axios.$get(
        "https://61981d74164fa60017c22f73.mockapi.io/contact"
      );
      this.all = res;
      console.log(res);
    },
  },
  mounted() {
    this.getData();
  },
};
</script>
