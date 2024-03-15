<script setup>
import { ref, onMounted, computed, watch } from 'vue'

const todos = ref([])
const name = ref('')

const input_content = ref('')
const input_category= ref(null)

const todos_asc = computed(() => todos.value.slice().sort((a, b) => {
  return b.createdAt - a.createdAt;
}));

const addTodo = () => {
  if (input_content.value.trim() === '' || !input_category.value === null) {
    console.log('Please fill in the input and select a category')
    return
  }
  todos.value.push({
    content: input_content.value,
    category: input_category.value,
    done: false,
    createdAt: new Date().getTime()
  })
  console.log('todo added')
  input_content.value = ''
  input_category.value = null
}

const removeTodo = (todo) => {
  todos.value = todos.value.filter(t => t !== todo)
}

watch(todos, (newVal) => {
  localStorage.setItem('todos', JSON.stringify(newVal))
}, { deep: true })

watch(name, (newVal) => {
  localStorage.setItem('name', newVal)
})

onMounted(() => {
  name.value = localStorage.getItem('name') || ''
  todos.value = JSON.parse(localStorage.getItem('todos')) || []
})
</script>

<template>

  <main class="app">
    <section class="greeting">
      <h3 class="title">
        You can tell it's using local storage because if you refresh the page, it doesn't disappear.
      </h3>
    </section>

    <section class="create-todo">
      <h3>What would you like to add to your todo list?</h3>
      <form @submit.prevent="addTodo">
        <input 
        type="text" 
        placeholder="e.g. Go grocery shopping." 
        v-model="input_content"/>
        <h3>Pick a category</h3>
        <div class="options">
            <label>
              <input 
              type="radio" 
              name="category"
              value="business" 
              v-model="input_category"/>
              <span class="bubble business"></span>
              <div>Business</div>
            </label>
            <label>
              <input 
              type="radio" 
              name="category"
              value="personal" 
              v-model="input_category"/>
              <span class="bubble personal"></span>
              <div>Personal</div>
            </label>
          </div>
        <input type="submit" value="Add todo">
      </form>
    </section>
    <section class="todo-list">
      <h3>Todo List</h3> 
      <div class="list">

        <div v-for="todo in todos_asc" :key="todo.createdAt" :class="`todo-item ${todo.done && 'done'}`">

          <label>
            <input type="checkbox" v-model="todo.done" />
            <span :class="`bubble ${todo.category}`"></span>
          </label>

          <div class="todo-content">
            <input type="text" v-model="todo.content" />
          </div>

          <div class="actions">
            <button class="delete" @click="removeTodo(todo)">Delete</button>
          </div>  
        </div>
      </div>
    </section>  
  </main>

</template>