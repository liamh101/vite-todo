<template>
  <li :class="{'checked': completed}"><input v-model="completed" type="checkbox"> {{message}} - {{added}}</li>
</template>

<script lang="ts">
import {defineComponent} from "vue";

export default defineComponent({
  name: "TodoItem",
  data() {
    return {
      completed: false,
    };
  },
  props: {
    message: String,
    added: String,
  },
  methods: {
    check() {
      this.completed = !this.completed;
    }
  }
})
</script>

<style scoped lang="scss">
    .checked {
      color: green;
    }
</style>