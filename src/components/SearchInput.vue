<template>
  <div class="input-container">
    <input 
      type="text"
      class="input"
      :value="value"
      placeholder="type a search term and click 'enter'"
      v-on="listeners"
    />
  </div>
</template>

<script>
  export default {
    name: 'SearchInput',
    props: {
      value: {
        type: String,
        default: '',
      }
    },
    computed: {
      listeners () {
        return {
          ...this.$listeners,
          input: event => this.$emit('input', event.target.value)
        }
      }
    }
  }
</script>

<style>
  .input-container {
    width: 70%;
  }
  .input {
    border: 1px solid;
    font-size: 1rem;
    height: 2rem;
    padding: 8px 10px;
    width: 100%;
  }
</style>
