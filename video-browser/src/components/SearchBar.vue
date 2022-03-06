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
      setTimeout(() => {
        this.$emit('termChange', event.target.value);
      }, 4000);
    }
  }
}
</script>

<style scoped>
  input {
    width: 75%;
  }

  div {
    text-align: center;
    margin: 20px;
  }
</style>