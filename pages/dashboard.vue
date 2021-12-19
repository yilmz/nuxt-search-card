<template>
  <v-row>
    <v-col v-for="item in items" :key="item.id" md="4" class="text-center">
      <Card :post="item" />
    </v-col>
  </v-row>
</template>

<script>
export default {
  name: "DashboardPage",
  data() {
    return {
      items: [],
    };
  },
  mounted() {
    fetch("https://jsonplaceholder.typicode.com/posts")
      .then((response) => response.json())
      .then((json) => (this.items = json));
  },
  created() {
    this.$nuxt.$on("open-dynamic-search", (searchText) => {
      this.items = this.items.filter(
        (item) => item.title.indexOf(searchText.toLowerCase()) > -1
      );
    });
  },
};
</script>
