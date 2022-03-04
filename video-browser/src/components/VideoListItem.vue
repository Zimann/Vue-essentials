<template>
  <li class="list-group-item">
    <img :src="thumbNailUrl">
    {{video.snippet.title}}
  </li>
</template>
<script>
export default {
  name: 'VideoListItem',
  props: ['video'],
  computed: {
    thumbNailUrl() {
      return this.video.snippet.thumbnails.default.url;
    }
  }
}
</script>
<style></style>