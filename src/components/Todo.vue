<template>
    <div>
        <h1>Todo App</h1>
        <label for="input"> Add todo
            <input type="text" id="input" v-model="newTodoText"/>
        </label>
        <ol>
            <li v-for="(todo, key) of todos" :key="key" :todo="todo"> {{ todo }} </li>
        </ol>
        <button @click="addTodo">Add</button>
        <button @click="removeTodo">Remove</button>
    </div>
</template>

<script>
    export default {
        name: "Todo",
        props: ['todo'],

        data() {
            return {
                newTodoText: '',
                todos: [],
            }
        },

        methods: {
            addTodo() {
              this.todos.push(this.newTodoText);
            },

            removeTodo() {
                this.todos.pop()
            }
        }
    }
</script>

<style scoped>

</style>