<template>
  <div class="bg-white p-2 flex w-full items-center space-x-5 md:w-full outline outline-slate-300">

    <button v-if="!isEditing" type="button" :class="{completed}" @click="$emit('on-complete')"
      class="rounded-md w-1/2 bg-white px-3 py-2 text-sm font-semibold text-black focus-visible:outline focus-visible:outline-2 focus-visible:outline-offset-2">
      {{ todoString }}
    </button>

    <form v-else @submit.prevent="endEditing()" id="form"
    class="w-1/2"
    >
      <input 
        v-model="newTodoString"
        @blur="startEditing()"
        class="flex h-10 w-full rounded-md border border-black/30 bg-transparent px-3 py-2 text-sm placeholder:text-gray-600 focus:outline-none focus:ring-1 focus:ring-black/30 focus:ring-offset-1 disabled:cursor-not-allowed disabled:opacity-50"
        type="text" placeholder="New Todo Item" />
    </form>

    <button type="button" @click="startEditing()"
      class="rounded-md bg-blue-500 px-3 py-1 text-sm font-semibold text-white shadow-sm hover:bg-blue-500/80 focus-visible:outline focus-visible:outline-2 focus-visible:outline-offset-2 focus-visible:outline-black">
      Edit
    </button>

    <button type="button" @click="$emit('on-delete')"
      class="rounded-md bg-red-800 px-3 py-1 text-sm font-semibold text-white shadow-sm hover:bg-red-800/80 focus-visible:outline focus-visible:outline-2 focus-visible:outline-offset-2 focus-visible:outline-black">
      Delete
    </button>
  </div>
</template>

<script>
export default {
  name: "TodoItem",
  data() {
    return {
      isEditing: false,
      newTodoString: "",

    }
  },
  props: {
    todoString: String,
    completed: Boolean
  },

  methods: {
    startEditing() {
      if (!this.isEditing) {
        this.newTodoString = this.todoString;
        this.isEditing = true;
      } 
      else {
        this.endEditing();
      }
    },
    endEditing() {
      this.isEditing = false;
      this.$emit("on-edit", this.newTodoString);
      console.log()
    }
  }
}
</script>

<style>
.completed {
  text-decoration-line: line-through;

}
</style>