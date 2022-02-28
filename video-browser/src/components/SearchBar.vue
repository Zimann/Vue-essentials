<template>
  <div>
    <input @input="onInput" type="text">
  </div>
</template>

<script>
export default {
  name: 'SearchBar',
  props: {
    text: String,
  },
  methods: {
    onInput(event){
      this.$emit('termChange', event.target.value);
    }
  }
}
</script>

<style scoped>

</style>