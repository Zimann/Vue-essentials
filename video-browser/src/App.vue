<template>
  <div>
    <SearchBar @termChange="onTermChange">
    </SearchBar>
    <VideoList :videos="videos"/>
  </div>
</template>

<script>
import axios from 'axios';
import SearchBar from "@/components/SearchBar";
import VideoList from "@/components/VideoList";
const API_KEY = 'AIzaSyC9pBPv7a8mMr2hj-Zu0goiFOQbB3nvQ0A';

export default {
  name: 'App',
  data() {
    return {
      searchData: 'search data',
      videos: [],
    }
  },
  components: {
    SearchBar,
    VideoList
  },
  methods: {
    onTermChange(searchTerm) {
      axios.get('https://www.googleapis.com/youtube/v3/search', {
        params: {
          key: API_KEY,
          type: 'video',
          part: 'snippet',
          q: searchTerm
        }
      }).then(response =>
          {
            console.log(response.data.items[0].snippet);
            console.log(response.data.items[0].snippet.description);
            this.videos = this.data = response.data.items;
          }
      );
    },
  }
}
</script>

<style>

</style>