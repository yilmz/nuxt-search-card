<template>
  <v-app dark>
    <v-app-bar v-if="$route.name != 'index'"  fixed app>
      <v-toolbar-title v-text="title" />
      <v-spacer />
      <v-text-field
        ref="searchText"
        hide-details
        label="Seach"
        v-model="searchCard"
      ></v-text-field>

      <v-spacer />
      <v-btn to="/dashboard">
        <v-icon left>mdi-application-cog-outline</v-icon> Dashboard
      </v-btn>
      <v-btn to="/inspire">
        <v-icon left>mdi-account-box</v-icon> Profil
      </v-btn>
    </v-app-bar>
    <v-main>
      <v-container fill-height pa-0>
        <Nuxt />
      </v-container>
    </v-main>

    <v-footer :absolute="!fixed" app>
      <span>&copy; {{ new Date().getFullYear() }}</span>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  name: "DefaultLayout",
  data() {
    return {
      searchCard: null,
      drawer: false,
      fixed: false,
      title: "Search Card",
    };
  },
  watch: {
    searchCard: function (searchText) {
      $nuxt.$emit("open-dynamic-search", searchText);
    },
  },
};
</script>
