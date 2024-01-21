<template>
    <div class="bg-white p-2 flex w-full items-center space-x-5 md:w-full outline outline-slate-300">
        <form @submit.prevent="addTodoItem()" class="w-full">
            <input v-model="newTodoString"
                class="flex h-10 w-full rounded-md border border-black/30 bg-transparent px-3 py-2 text-sm placeholder:text-gray-600 focus:outline-none focus:ring-1 focus:ring-black/30 focus:ring-offset-1 disabled:cursor-not-allowed disabled:opacity-50"
                type="text" placeholder="New item" />
        </form>
    </div>
</template>

<script>
export default {
    name: "NewTodo",
    data() {
        return {
            newTodoString: "",

        }
    },
    methods: {
        addTodoItem() {
            if (this.newTodoString.length > 1) {
                this.$emit("on-add", this.newTodoString);
            }
            this.newTodoString = "";
        }
    }

}
</script>
