<template>
  <div class="container">
    <SearchBar @termChange="onTermChange">
    </SearchBar>
    <div class="row">
      <VideoDetail :video="selectedVideo" />
      <VideoList :videos="videos" @videoSelect="onVideoSelect"/>
    </div>
  </div>
</template>

<script>
import axios from 'axios';
import SearchBar from "@/components/SearchBar";
import VideoList from "@/components/VideoList";
import VideoDetail from "@/components/VideoDetail";
const API_KEY = 'AIzaSyB5zaqvXBiZ4AvBfIoIsKRgx4zPp8ZH7Sc';

export default {
  name: 'App',
  data() {
    return {
      searchData: 'search data',
      videos: [],
      selectedVideo: null
    }
  },
  components: {
    VideoDetail,
    SearchBar,
    VideoList,
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
      this.selectedVideo = video;
    }
  }
}
</script>

<style>

</style>