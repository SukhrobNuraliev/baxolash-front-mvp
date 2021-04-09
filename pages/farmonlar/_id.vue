<template>
  <div>
    <div class="bg-white m-4 p-5 rounded rounded-md shadow shadow-lg">
      <h5 class="font-bold text-blue-500">Farmon:</h5>
      “RAQAMLI O‘ZBEKISTON — 2030” STRATEGIYASINI TASDIQLASH VA UNI SAMARALI AMALGA OSHIRISH CHORA-TADBIRLARI TO‘G‘RISIDA
    </div>

    <vue-tabs class="items-center mt-6 max-w-6xl m-5">
        <v-tab class="p-4 salamn" title="Farmonga Ilova qo'shish">
            <div class="bg-white shadow-md rounded px-8 pt-6 pb-8 mb-4 flex flex-col my-2">
              <form v-for="ilova in ilovas" @submit.prevent="createIlova">
                <div class="-mx-3 border border-gray-200 mb-6 md:flex p-8 rounded rounded-lg shadow-md">
                  <div class="md:w-1/2 px-3">
                    <label class="block uppercase tracking-wide text-grey-darker text-xs font-bold mb-2" for="grid-last-name">
                      Soni
                    </label>
                    <input name="ilova-number" class="appearance-none block w-full bg-grey-lighter text-grey-darker border border-grey-lighter rounded py-3 px-4" id="grid-last-name" type="text">
                  </div>
                  <div class="md:w-1/2 px-3 mb-6 md:mb-0">
                    <label class="block uppercase tracking-wide text-grey-darker text-xs font-bold mb-2" for="grid-first-name">
                      Nomi
                    </label>
                    <input name="ilova-name" class="appearance-none block w-full bg-grey-lighter text-grey-darker border border-red rounded py-3 px-4 mb-3" id="grid-first-name" type="text" >
                  </div>
                  <div class="flex items-center">
                    <button v-show="ilavaCreated" type="submit" class="h-10 bg-indigo-500 focus:outline-none font-medium hover:bg-indigo-600 hover:shadow-lg inline-block leading-6 ml-5 nuxt-link-active pl-8 pr-8 px-6 py-2 ripple rounded shadow text-center text-white text-xs transition uppercase waves-effect">Qo'shish</button>
                  </div>
                </div>
              </form>
                <div class="flex flex-col">
                  <form v-for="band in bands" @submit.prevent="createBand" class="flex justify-end">
                    <div class="-mx-3 border border-gray-200 mb-6 md:flex p-8 rounded rounded-lg shadow-md">
                    <h6>band</h6>
                      <div class="md:w-1/2 px-3">
                        <label class="block uppercase tracking-wide text-grey-darker text-xs font-bold mb-2" for="grid-last-name">
                          Soni
                        </label>
                        <input name="ilova-number" class="appearance-none block w-full bg-grey-lighter text-grey-darker border border-grey-lighter rounded py-3 px-4" id="grid-last-name" type="text">
                      </div>
                      <div class="md:w-1/2 px-3 mb-6 md:mb-0">
                        <label class="block uppercase tracking-wide text-grey-darker text-xs font-bold mb-2" for="grid-first-name">
                          Nomi
                        </label>
                        <input name="ilova-name" class="appearance-none block w-full bg-grey-lighter text-grey-darker border border-red rounded py-3 px-4 mb-3" id="grid-first-name" type="text" >
                      </div>
                      <div class="flex items-center">
                        <button type="submit" class="h-10 bg-indigo-500 focus:outline-none font-medium hover:bg-indigo-600 hover:shadow-lg inline-block leading-6 ml-5 nuxt-link-active pl-8 pr-8 px-6 py-2 ripple rounded shadow text-center text-white text-xs transition uppercase waves-effect">
                          +
                        </button>
                      </div>
                    </div>
                  </form>
                  <div class="flex justify-end">
                  <button v-show="showBandButton" @click="addBand" class="border border-gray-600 focus:outline-none hover:bg-gray-50 mb-5 mr-52 px-5 py-2.5 rounded-md text-gray-600 text-sm w-64">
                    band qo'shish
                  </button>
                  </div>
                </div>
          <button @click="addIlova" class="focus:outline-none text-gray-600 text-sm py-2.5 px-5 rounded-md border border-gray-600 hover:bg-gray-50">
            yangi ilova
          </button>
            </div>
        </v-tab>

        <v-tab title="Farmonga Band qo'shish">
          <div class="bg-white shadow-md rounded px-8 pt-6 pb-8 mb-4 flex flex-col my-2">
            <div class="-mx-3 md:flex mb-6">
              <div class="md:w-1/2 px-3 mb-6 md:mb-0">
                <label class="block uppercase tracking-wide text-grey-darker text-xs font-bold mb-2" for="grid-first-name">
                  First Name
                </label>
                <input class="appearance-none block w-full bg-grey-lighter text-grey-darker border border-red rounded py-3 px-4 mb-3" id="grid-first-name" type="text" placeholder="Jane">
                <p class="text-red text-xs italic">Please fill out this field.</p>
              </div>
              <div class="md:w-1/2 px-3">
                <label class="block uppercase tracking-wide text-grey-darker text-xs font-bold mb-2" for="grid-last-name">
                  Last Name
                </label>
                <input class="appearance-none block w-full bg-grey-lighter text-grey-darker border border-grey-lighter rounded py-3 px-4" id="grid-last-name" type="text" placeholder="Doe">
              </div>
            </div>
            <div class="-mx-3 md:flex mb-6">
              <div class="md:w-full px-3">
                <label class="block uppercase tracking-wide text-grey-darker text-xs font-bold mb-2" for="grid-password">
                  Password
                </label>
                <input class="appearance-none block w-full bg-grey-lighter text-grey-darker border border-grey-lighter rounded py-3 px-4 mb-3" id="grid-password" type="password" placeholder="******************">
                <p class="text-grey-dark text-xs italic">Make it as long and as crazy as you'd like</p>
              </div>
            </div>
            <div class="-mx-3 md:flex mb-2">
              <div class="md:w-1/2 px-3 mb-6 md:mb-0">
                <label class="block uppercase tracking-wide text-grey-darker text-xs font-bold mb-2" for="grid-city">
                  City
                </label>
                <input class="appearance-none block w-full bg-grey-lighter text-grey-darker border border-grey-lighter rounded py-3 px-4" id="grid-city" type="text" placeholder="Albuquerque">
              </div>
              <div class="md:w-1/2 px-3">
                <label class="block uppercase tracking-wide text-grey-darker text-xs font-bold mb-2" for="grid-state">
                  State
                </label>
                <div class="relative">
                  <select class="block appearance-none w-full bg-grey-lighter border border-grey-lighter text-grey-darker py-3 px-4 pr-8 rounded" id="grid-state">
                    <option>New Mexico</option>
                    <option>Missouri</option>
                    <option>Texas</option>
                  </select>
                  <div class="pointer-events-none absolute pin-y pin-r flex items-center px-2 text-grey-darker">
                    <svg class="h-4 w-4" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 20 20"><path d="M9.293 12.95l.707.707L15.657 8l-1.414-1.414L10 10.828 5.757 6.586 4.343 8z"/></svg>
                  </div>
                </div>
              </div>
              <div class="md:w-1/2 px-3">
                <label class="block uppercase tracking-wide text-grey-darker text-xs font-bold mb-2" for="grid-zip">
                  Zip
                </label>
                <input class="appearance-none block w-full bg-grey-lighter text-grey-darker border border-grey-lighter rounded py-3 px-4" id="grid-zip" type="text" placeholder="90210">
              </div>
            </div>
          </div>
        </v-tab>
    </vue-tabs>

  </div>
</template>

<script>
export default {
  data() {
    return {
      ilovas: [1],
      bands: [],
      showBandButton: false,
      ilavaCreated: true,
    }
  },
  methods: {
    createIlova(){
      this.showBandButton = true
      this.ilavaCreated = false
      return 'created'
    },
    addIlova(){
      this.ilovas.push(1)
    },
    createBand(){
      return 'asdf'
    },
    addBand(){
        this.bands.push(1)
    }
  }
}
</script>
