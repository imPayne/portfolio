<template>
  <div class="mt-44 flex flex-col items-center h-screen">
    <div class="shadow-2xl border-2 border-black w-auto h-auto m-6 px-20 py-10 rounded-md flex flex-col items-start content-start">
      <form class="flex items-center mt-10" @submit.prevent="addItem">
        <input class="rounded-l-lg p-4 border-t mr-0 border-b border-l text-gray-800 border-gray-200 bg-white" type="text" placeholder="Nouvelle Todo..." v-model="newItem" />
        <button class="px-8 rounded-r-lg bg-green-500 text-black font-bold p-4 uppercase border-green-500 border-t border-b border-r transition-all duration-300 hover:bg-blue-500 hover:text-white hover:scale-110 hover:rotate-12" type="submit">Ajouter</button>
      </form>
      <div class="mt-8">
        <h2 class="text-lg font-bold mb-2">Les Todos: </h2>
        <div class="h-auto w-64 flex flex-col star">
          <div class="bg-gray-200 mx-2 my-2 p-4 rounded-md" v-for="(item, index) in items" :key="index">{{ item }}</div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      newItem: '',
      items: []
    }
  },
  methods: {
    addItem() {
      if (this.newItem !== '') {
        this.items.push(this.newItem)
        this.newItem = ''
      }
    }
  }
}
</script>

<style scoped>
button:hover {
  transform-origin: center;
}
</style>
