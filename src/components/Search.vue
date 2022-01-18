<template>
  <div class="search">
      <input
      id="search"
      v-model="inputText" 
      placeholder="Search genre"
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

<style lang="scss">
    .search {
        width: 30%;
        margin: 0 auto;
        padding-top: 2em;
    
        input {
            width: 100%;
            margin: 0 auto;
            border-radius: 10px;
            border-style: none;
            outline-color: #1ed760;
        }
    }


</style>