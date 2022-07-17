<template>
  <form>
    <input type="text" v-model="name" />
    <button class="" @click.prevent="submit">Submit</button>

    <p v-if="error" class="todo-error" v-text="error"></p>
  </form>
</template>

<script lang="ts">
import {defineComponent} from "vue";

export default defineComponent({
  name: "TodoForm",
  data() {
    return {
      name: '',
      error: '',
    }
  },
  methods: {
    submit() {
      if (!this.name) {
        this.error = 'Must Define a name';
        return;
      }

      this.error = '';

      this.$emit('submitted', this.name);
      this.name = '';
    }
  }
})
</script>

<style scoped>
  .button-margin {
    margin-left: 5px;
  }

  .todo-error {
    color: red;
  }
</style>