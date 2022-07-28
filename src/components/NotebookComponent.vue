<template>
  <div class="notebook">
    <v-card class="mx-auto" max-width="400" tile>
      <v-list>
        <v-list-item
          v-for="(page, index) in pages"
          :key="index"
          :class="{ active: index === activePage }"
          @click="changePage(index)"
        >
          <v-list-item-title v-text="page.title"></v-list-item-title>
        </v-list-item>
      </v-list>
      <!-- <li class="new-page" @click=newPage()">New Page</li> -->
      
    </v-card>
  </div>
</template>

<script>
export default {
  name: "NotebookComponent",
  props: ["pages", "activePage"],
  methods: {
    changePage(index) {
      this.$emit("change-page", index);
    },
    newPage() {
      this.$emit("new-page");
    },
  },
};
</script>

<style scoped></style>
