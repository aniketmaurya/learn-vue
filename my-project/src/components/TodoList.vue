<template>
    <h1 class="text-2xl">ToDo List</h1>
    <div class="text-black p-2 rounded-md">
        <NewTodo 
            @on-add="addTodo($event)"
        />
        <ul>
            <TodoItem v-for="(todo, index) in todos" :key="index" 
                :todoString="todo.todoString" 
                :completed="todo.completed"
                @on-delete="deleteTodo(todo)"
                @on-complete="toggleTodo(todo)"
                @on-edit="editTodo(todo, $event)"
            />
        </ul>
</div>

</template>

<script>
import NewTodo from './NewTodo.vue';
import TodoItem from './TodoItem.vue';

export default {
    name: "TodoList",
    components: {
        TodoItem,
        NewTodo
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
            todo.todoString = newTodoString;

        },
        deleteTodo(deleteTodo) {
            this.todos = this.todos.filter(todo => todo !== deleteTodo);
        }

    },
}
</script>

