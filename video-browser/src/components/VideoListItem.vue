<template>
  <div></div>
  <li>
    {{video.snippet.title}}
  </li>
</template>
<script>
export default {
  name: 'VideoListItem',
  props: ['video']
}
</script>
<style></style>