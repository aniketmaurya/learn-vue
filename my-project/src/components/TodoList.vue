<template>
    <h1>ToDo List</h1>
    <div>
        <ul>
            <TodoItem v-for="(todo, index) in todos" :key="index" 
                :todoString="todo.todoString" 
                :completed="todo.completed"
            />
        </ul>

    
</div>

</template>

<script>
import TodoItem from './TodoItem.vue';

export default {
    name: "TodoList",
    components: {
        TodoItem
    },

    data() {
        return {
            todos: [
                { todoString: "Take dog for walk", completed: true },
                { todoString: "Drink water", completed: false },
                { todoString: "Cook dinner", completed: false },
                { todoString: "Learn Vue", completed: true }

            ]

        }
    },
    methods: {
        addTodo(newTodo) {
            this.todos.push({ todoString: newTodo, completed: false })

        },
        toggleTodo(todo) {
            todo.completed = !todo.completed;
        },
        editTodo(todo, newTodoString) {
            todo.todoString = newTodoString

        },
        deleteTodo(deleteTodo) {
            this.todos = this.todos.filter(todo => todo !== deleteTodo);
        }

    },
}
</script>

