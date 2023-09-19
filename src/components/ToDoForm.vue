<template>
  <form @submit.prevent="onSubmit">
    <label for="new-todo-input" class="label__lg"> What needs to be done? </label>
    <input
      type="text"
      name="new-todo"
      id="new-todo-input"
      autocomplete="off" 
      v-model="label"
      class="input__lg"
    />
    <button type="submit" class="btn btn__primary btn__lg">Add</button>
  </form>
</template>

<script>

export default {
  methods: {
    onSubmit() {
      if (this.label == '') {
        return
      }
      this.$emit('todo-added', this.label)
      this.label == ''
      
    }
  },
  data() {
    return {
      label: ''
    }
  }
}
</script>

<style>

</style>
