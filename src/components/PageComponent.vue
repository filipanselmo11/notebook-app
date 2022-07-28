<template>
  <div class="page">
    <div v-if="page">
      <v-text-field 
        v-model="pageComp"
        label="Enter a title" 
        hide-details="auto"></v-text-field>
        <br/>
        <v-textarea 
          name="input-7-1" 
          filled 
          label="Enter some content"
          auto-grow></v-textarea>
          <br/>
          <v-btn @click="deletePage">Delete Page</v-btn>
          <v-btn @click="savePage">Save Page</v-btn>
    </div>
    <div v-else>
      <h1>To start, create a new page!</h1>
    </div>
  </div>
</template>

<script>
export default {
  name: 'PageComponent',
  props:['page'],
  data:() => ({
    pageComp: '',
  }),
  methods:{
    deletePage() {
      this.$emit('delete-page');
    },
    savePage() {
      this.$emit('save-page');
    }
  },
}
</script>

<style>

</style>