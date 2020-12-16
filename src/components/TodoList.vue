<template>
  <div>
    <ul>
      <TodoItem 
        v-for="(todo, index) in todos" :key="index"
        v-bind:index="index"
        v-bind:todo="todo"
        @remove-todo="removeTodo"
      />
    </ul>
  </div>
</template>

<script>
import TodoItem from "@/components/TodoItem";
export default {
  props: ['todos'],
  components: {
    TodoItem,
  },
  methods: {
    removeTodo(id) {
      this.$emit('remove-todo', id)
    }
  }
};
</script>

<style lang="scss" scoped>
  ul {
    list-style: none;
    margin: 0;
    padding: 0;
  }
</style>