<template>
    <div class="container">
        <h1>Todo App</h1>
        <label for="input"> Add todo
            <input id="input" v-model="newTodoText"/>
        </label>
        <ul>
            <li v-for="(todo, key) of todos"
                :key="key"
                :todo="todo"
            >
                {{ todo }}
                <button @click="removeTodo(todo)"> remove </button>
            </li>
        </ul>
        <button @click="addTodo" @click.enter="">Add</button>
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
                this.newTodoText = ''
            },

            removeTodo(removeTodoItem) {
               this.todos = this.todos.filter((todo) => {
                    return todo !== removeTodoItem
                });
            },
        },
    }
</script>

<style scoped>

</style>