<script>
import ToDoList from './components/ToDoList'
import CreateToDo from './components/CreateToDo'

export default {
  components: {
    ToDoList,
    CreateToDo
  },
  data () {
    return {
      todos: [{ // this will be bound to the ToDoList's todo var
        id: 1, // the id is added because v-for needs an ID from the child components
        title: 'Todo A',
        project: 'Project A',
        done: false
      }, {
        id: 2,
        title: 'Todo B',
        project: 'Project B',
        done: true
      }, {
        id: 3,
        title: 'Todo C',
        project: 'Project C',
        done: false
      }, {
        id: 4,
        title: 'Todo D',
        project: 'Project D',
        done: false
      }]
    }
  },
  methods: {
    addTodo (todo) {
      debugger
      this.todos.push({
        title: todo.title,
        project: todo.project,
        done: todo.done
      })
    }
  }
}
</script>

<template>
  <div>
    <to-do-list v-bind:todos="todos"></to-do-list>
    <create-to-do v-on:add-todo="addTodo"></create-to-do>
  </div>
</template>
