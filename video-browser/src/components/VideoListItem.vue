<template>
  <div></div>
  <li>
    {{videoItem.snippet.description}}
  </li>
</template>
<script>
export default {
  name: 'VideoListItem',
  props: ['videoItem']
}
</script>
<style></style>