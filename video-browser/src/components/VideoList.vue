<template>
    <ul class="list-group">
      <VideoListItem
          v-for="video of videos"
          :video="video"
          :key="video.etag"
          @videoSelect="onVideoSelect"
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
    onVideoSelect(video) {
      this.$emit('videoSelect', video);
    }
  }
}
</script>

<style scoped>

</style>