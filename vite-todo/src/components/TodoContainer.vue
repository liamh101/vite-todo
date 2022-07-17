<template>
  <div >
    <ul class="">
      <li class="flex justify-center" v-for="item in items">{{item.name}}</li>
<!--          <todo-item v-for="item in items" :message="item.name" :added="item.added"/>-->
    </ul>

    <TodoForm @submitted="newItem" class="flex justify-center"></TodoForm>
  </div>

</template>

<script lang="ts">
import {defineComponent} from "vue";
import TodoForm from "./TodoForm.vue";
import TodoItem from "./TodoItem.vue";
import { DateTime } from "luxon";


export default defineComponent({
  name: "TodoContainer",
  components: {TodoItem, TodoForm},
  data() {
    return {
      items: [{ name: 'Hello world', added: DateTime.now().toLocaleString(DateTime.DATE_SHORT)} ],
    }
  },
  methods: {
    newItem(item: string) {
      this.items.push({ name: item, added: DateTime.now().toLocaleString(DateTime.DATE_SHORT)});
    },
    removeItem(index: number) {
      this.items.splice(index, 1);
    }
  }
})
</script>

<style scoped>
  .no-bullets {
    list-style-type: none;
  }
</style>