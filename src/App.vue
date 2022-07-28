<template>
  <v-app>
    <v-main>
      <notebook-component
        @change-page="changePage"
        :pages="pages"
        :activePage="index"
      ></notebook-component>
      <page-component
        @save-page="savePage"
        @delete-page="deletePage"
        :page="pages[index]"
      ></page-component>
    </v-main>
  </v-app>
</template>

<script>
import NotebookComponent from "./components/NotebookComponent.vue";
import PageComponent from "./components/PageComponent.vue";
export default {
  name: "App",

  components: { NotebookComponent, PageComponent },

  data: () => ({
    pages: [],
    index: 0,
  }),

  methods: {
    newPage() {
      this.pages.push({
        title: "",
        content: "",
      });
      this.index = this.pages.length - 1;
    },

    changePage(index) {
      this.index = index;
    },

    savePage() {

    },
    deletePage() {
      this.pages.splice(this.index, 1);
      this.index = Math.max(this.index - 1, 0);
    }
  },
};
</script>
