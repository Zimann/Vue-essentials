<template>
  <div class="container">
    <SearchBar @termChange="onTermChange">
    </SearchBar>
    <VideoList :videos="videos" @videoSelect="onVideoSelect"/>
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
            this.videos = this.data = response.data.items;
          }
      );
    },
    onVideoSelect(video) {
      console.log(video);
    }
  }
}
</script>

<style>

</style>