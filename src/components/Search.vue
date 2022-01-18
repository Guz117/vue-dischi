<template>
  <div class="search">
      <input
      id="search"
      v-model="inputText" 
      @keyup.enter="sendSearch()"
      type="text"
      name="search"
      >
  </div>
</template>

<script>
export default {
    name: 'Search',
    data() {
        return {
            inputText: '',
        };
    },
    methods: {
        sendSearch() {
            this.$emit('doSearch', this.inputText);
        }
    }
}
</script>

<style>

</style>