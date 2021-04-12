<template>
  <div class="flex items-center min-h-screen bg-gray-50 dark:bg-gray-900">
    <div class="container mx-auto">
        <div class="max-w-screen-lg mx-auto my-10 bg-white p-5 rounded-md shadow-sm">
            <div class="text-center">
                <h1 class="my-3 text-3xl font-semibold text-gray-700 dark:text-gray-200">Farmon Qo'shish</h1>
            </div>
            <div class="m-7">
                <form id="form" @submit.prevent="createFarmon">

                    <div class="mb-6">
                        <label for="name" class="block mb-2 text-sm text-gray-600 dark:text-gray-400">Nomi</label>
                        <input type="text" name="name" id="name" placeholder="......" class="w-full px-3 py-2 placeholder-gray-300 border border-gray-300 rounded-md focus:outline-none focus:ring focus:ring-indigo-100 focus:border-indigo-300 dark:bg-gray-700 dark:text-white dark:placeholder-gray-500 dark:border-gray-600 dark:focus:ring-gray-900 dark:focus:border-gray-500" />
                    </div>
                  <div class="flex items-center justify-between">
                    <div class="mb-6 w-full">
                        <label for="farmon-number" class="text-sm text-gray-600 dark:text-gray-400">Raqami</label>
                        <input type="text" name="farmon-number" id="farmon-number" placeholder="PX-526" class="w-full px-3 py-2 placeholder-gray-300 border border-gray-300 rounded-md focus:outline-none focus:ring focus:ring-indigo-100 focus:border-indigo-300 dark:bg-gray-700 dark:text-white dark:placeholder-gray-500 dark:border-gray-600 dark:focus:ring-gray-900 dark:focus:border-gray-500" />
                    </div>
                    <div class="mb-6 ml-3 w-full">
                        <label for="date" class="block mb-2 text-sm text-gray-600 dark:text-gray-400">Sanasi</label>
                        <input type="date" name="date" id="date" placeholder="04/11/2021" class="w-full px-3 py-2 placeholder-gray-300 border border-gray-300 rounded-md focus:outline-none focus:ring focus:ring-indigo-100 focus:border-indigo-300 dark:bg-gray-700 dark:text-white dark:placeholder-gray-500 dark:border-gray-600 dark:focus:ring-gray-900 dark:focus:border-gray-500" />
                    </div>
                  </div>
                    <div class="mb-6">
                        <div class="border border-dashed border-gray-500 relative">
                          <input type="file" multiple class="cursor-pointer relative block opacity-0 w-full h-full p-12 z-50">
                          <div class="text-center p-7 absolute top-0 right-0 left-0 m-auto">
                              <h4>
                                  Fayl ni tashlang
                                  <br/>yoki
                              </h4>
                              <p class="">Tanlang</p>
                          </div>
                        </div>
                    </div>
                    <div class="mb-6">
                        <button type="submit" class="w-full px-3 py-4 text-white bg-indigo-500 rounded-md focus:bg-indigo-600 focus:outline-none">Qo'shish</button>
                    </div>
                    <p class="text-base text-center text-gray-400" id="result">
                    </p>
                </form>
            </div>
        </div>
    </div>
</div>
</template>

<script>
export default {
  data(){
    return {
      farmon: {
        name: '',
        number: '',
        date: '',
      }
    }
  },
  methods: {
    createFarmon(){
      this.$router.push('/farmonlar/12')
    }
  }

}
</script>
