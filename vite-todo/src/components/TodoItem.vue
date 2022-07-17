<template>
  <li class="flex justify-center bg-gradient-to-r from-indigo-500 via-purple-500 to-pink-500 mx-100" :class="{'checked': completed}"><input v-model="completed" type="checkbox"> {{message}} - {{added}}</li>
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
  }
})
</script>

<style scoped lang="scss">
    .checked {
      color: green;
    }
</style>