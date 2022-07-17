<template>
  <form>
    <input class="rounded-md" type="text" v-model="name" />
    <button class="py-2 px-3 ml-5 bg-indigo-500 text-white text-sm font-semibold rounded-md shadow focus:outline-none" @click.prevent="submit">Submit</button>

    <p v-if="error" v-text="error"></p>
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

</style>