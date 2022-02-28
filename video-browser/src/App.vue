<template>
  <div>
    <SearchBar @termChange="onTermChange">
    </SearchBar>
  </div>
</template>

<script>
import SearchBar from "@/components/SearchBar";
const API_KEY = 'AIzaSyC9pBPv7a8mMr2hj-Zu0goiFOQbB3nvQ0A';

export default {
  name: 'App',
  data() {
    return {
      searchData: 'search data',
    }
  },
  components: {
    SearchBar
  },
  methods: {
    onTermChange(searchTerm) {
      console.log(searchTerm);
    },
  }
}
</script>

<style>

</style>