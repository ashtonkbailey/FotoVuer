<template>
  <div>
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
  .input {
    width: 100%;
    padding: 8px 10px;
    border: 1px solid
  }
</style>
