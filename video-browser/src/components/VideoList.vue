<template>
    <ul>
      <VideoListItem
          :key="video.snippet.channelId"
          v-for="video of videos"
          :videoItem="video"
      />
    </ul>
</template>

<script>
import VideoListItem from "@/components/VideoListItem";

export default {
  name: 'VideoList',
  components: {
    VideoListItem
  },
  props: {
    videos: Array,
  },
  methods: {
  }
}
</script>

<style>
</style>