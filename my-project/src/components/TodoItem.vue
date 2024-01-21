<template>
  <div class="flex w-full items-center space-x-2 md:w-full">

    <button type="button" :class="{ 'line-through': completed }" @click="$emit('on-complete')"
      class="rounded-md bg-white px-3 py-2 text-sm font-semibold text-black focus-visible:outline focus-visible:outline-2 focus-visible:outline-offset-2">
      {{ todoString }}
    </button>

    <input
      class="flex h-10 w-full rounded-md border border-black/30 bg-transparent px-3 py-2 text-sm placeholder:text-gray-600 focus:outline-none focus:ring-1 focus:ring-black/30 focus:ring-offset-1 disabled:cursor-not-allowed disabled:opacity-50"
      type="text" placeholder="New Todo Item" 
    />

    <button type="button" @click="$emit('on-delete')"
      class="rounded-md bg-blue-500 px-3 py-2 text-sm font-semibold text-white shadow-sm hover:bg-blue-500/80 focus-visible:outline focus-visible:outline-2 focus-visible:outline-offset-2 focus-visible:outline-black">
      Edit
    </button>

    <button type="button" @click="$emit('on-delete')"
      class="rounded-md bg-red-800 px-3 py-2 text-sm font-semibold text-white shadow-sm hover:bg-red-800/80 focus-visible:outline focus-visible:outline-2 focus-visible:outline-offset-2 focus-visible:outline-black">
      Delete
    </button>
  </div>
</template>

<script>
export default {
  name: "TodoItem",
  data() {
    return {

    }
  },
  props: {
    todoString: String,
    completed: Boolean
  }
}
</script>
