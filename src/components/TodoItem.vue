<template>
  <li>
    <span :class="{done: todo.completed}">
      <input type="checkbox" @click="todo.completed = !todo.completed">
      <strong>{{ index + 1 }}</strong>
      {{ todo.title}}
    </span>
    <button class="btn" @click="$emit('remove-todo', todo.id)">&times;</button>
  </li>
</template>

<script>
export default {
  props: {
    todo: {
      type: Object,
      required: true,
    },
    index: Number
  },
};
</script>

<style lang="scss" scoped>
  li {
    border: 1px solid #ccc;
    display: flex;
    justify-content: space-between;
    padding: .5rem 2rem;
    margin-bottom: 1rem;
  }

  input {
    margin-right: 1rem;
  }

  .btn {
    background: red;
    color: #fff;
    border-radius: 50%;
    font-weight: bold;
    outline: none;
  }

  .done {
    text-decoration: line-through;
  }
</style>