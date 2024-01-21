<template>
  <!-- <div>
        {{ todoString }}
        <button>Complete</button>
        <button>Delete</button>
    </div> -->
  <div class="flex w-full items-center space-x-2 md:w-1/3">
    <input
      class="flex h-10 w-full rounded-md border border-black/30 bg-transparent px-3 py-2 text-sm placeholder:text-gray-600 focus:outline-none focus:ring-1 focus:ring-black/30 focus:ring-offset-1 disabled:cursor-not-allowed disabled:opacity-50"
      type="email" placeholder="Email" />
    <button type="button"
      class="rounded-md bg-black px-3 py-2 text-sm font-semibold text-white shadow-sm hover:bg-black/80 focus-visible:outline focus-visible:outline-2 focus-visible:outline-offset-2 focus-visible:outline-black">
      Subscribe
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

<style scoped></style>