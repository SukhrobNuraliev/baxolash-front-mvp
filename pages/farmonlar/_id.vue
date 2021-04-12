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
                    <button v-show="ilovaCreated" type="submit" class="h-10 bg-indigo-500 focus:outline-none font-medium hover:bg-indigo-600 hover:shadow-lg inline-block leading-6 ml-5 nuxt-link-active pl-8 pr-8 px-6 py-2 ripple rounded shadow text-center text-white text-xs transition uppercase waves-effect">
                      Qo'shish</button>
                  </div>
                </div>
              </form>
                <div class="flex flex-col">
                  <form v-for="band in bands" @submit.prevent="createBand" class="flex justify-end">
                    <div class="-mx-3 border border-gray-200 mb-6 p-8 rounded rounded-lg shadow-md">

                      <div class="flex">
                        <div class="md:w-1/2 px-3">
                          <label class="block uppercase tracking-wide text-grey-darker text-xs font-bold mb-2" for="grid-last-name">
                            Band Soni
                          </label>
                          <input name="ilova-number" class="appearance-none block w-full bg-grey-lighter text-grey-darker border border-grey-lighter rounded py-3 px-4" id="grid-last-name" type="text">
                        </div>
                        <div class="md:w-1/2 px-3 mb-6 md:mb-0">
                          <label class="block uppercase tracking-wide text-grey-darker text-xs font-bold mb-2" for="grid-first-name">
                            Topshiriq
                          </label>
                          <input name="ilova-name" class="appearance-none block w-full bg-grey-lighter text-grey-darker border border-red rounded py-3 px-4 mb-3" id="grid-first-name" type="text" >
                        </div>
                      </div>

                      <div class="flex">
                        <div class="md:w-1/2 px-3">
                          <label class="block uppercase tracking-wide text-grey-darker text-xs font-bold mb-2" for="grid-state">
                            Mas'ul Viloyat
                          </label>
                          <div class="flex items-center justify-end relative">
                            <select class="block appearance-none w-full bg-grey-lighter border border-grey-lighter text-grey-darker py-3 px-4 pr-8 rounded" id="grid-state">
                              <option>Andijon</option>
                              <option>Buxoro</option>
                              <option>Namangan</option>
                              <option>Farg'ona</option>
                            </select>
                            <div class="pointer-events-none absolute pin-y pin-r flex items-center px-2 text-grey-darker">
                              <svg class="h-4 w-4" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 20 20"><path d="M9.293 12.95l.707.707L15.657 8l-1.414-1.414L10 10.828 5.757 6.586 4.343 8z"/></svg>
                            </div>
                          </div>
                        </div>
                        <div class="md:w-1/2 px-3">
                          <label class="block uppercase tracking-wide text-grey-darker text-xs font-bold mb-2" for="grid-state">
                            Mas'ul Tuman
                          </label>
                          <div class="flex items-center justify-end relative">
                            <select class="block appearance-none w-full bg-grey-lighter border border-grey-lighter text-grey-darker py-3 px-4 pr-8 rounded" id="grid-state">
                              <option>Denov</option>
                              <option>Chinoz</option>
                              <option>Chust</option>
                              <option>Asaka</option>
                            </select>
                            <div class="pointer-events-none absolute pin-y pin-r flex items-center px-2 text-grey-darker">
                              <svg class="h-4 w-4" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 20 20"><path d="M9.293 12.95l.707.707L15.657 8l-1.414-1.414L10 10.828 5.757 6.586 4.343 8z"/></svg>
                            </div>
                          </div>
                        </div>
                      </div>

                      <div class="flex mt-3">
                        <div class="md:w-1/2 px-3">
                          <label class="block uppercase tracking-wide text-grey-darker text-xs font-bold mb-2" for="grid-state">
                            Mas'ul Organ
                          </label>
                          <div class="flex items-center justify-end relative">
                            <select class="block appearance-none w-full bg-grey-lighter border border-grey-lighter text-grey-darker py-3 px-4 pr-8 rounded" id="grid-state">
                              <option>Iqtisodiyot vazirligi</option>
                              <option>Moliya vazirligi</option>
                              <option>Davlat statistika qo‘mitasi</option>
                              <option>Intellektual mulk agentligi</option>
                            </select>
                            <div class="pointer-events-none absolute pin-y pin-r flex items-center px-2 text-grey-darker">
                              <svg class="h-4 w-4" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 20 20"><path d="M9.293 12.95l.707.707L15.657 8l-1.414-1.414L10 10.828 5.757 6.586 4.343 8z"/></svg>
                            </div>
                          </div>
                        </div>
                        <div class="md:w-1/2 px-3">
                            <label for="date" class="block uppercase tracking-wide text-grey-darker text-xs font-bold mb-2">Muddati</label>
                            <input type="date" name="date" id="date" placeholder="04/11/2021" class="w-full px-3 py-2 placeholder-gray-300 border border-gray-300 rounded-md focus:outline-none focus:ring focus:ring-indigo-100 focus:border-indigo-300 dark:bg-gray-700 dark:text-white dark:placeholder-gray-500 dark:border-gray-600 dark:focus:ring-gray-900 dark:focus:border-gray-500" />
                        </div>
                      </div>

                      <form v-for="bosqich in bosqichs" class="bg-gray-100 border flex ml-20 mt-5 p-2 py-3 rounded rounded-md">
                        <div class="border border-gray-300 flex font-black items-center p-2">1</div>
                        <div class="md:w-1/2 px-3">
                          <label class="block uppercase tracking-wide text-grey-darker text-xs font-bold mb-2" for="grid-last-name">
                            Nomi
                          </label>
                          <input name="ilova-number" class="appearance-none block w-full bg-grey-lighter text-grey-darker border border-grey-lighter rounded py-3 px-4" id="grid-last-name" type="text">
                        </div>
                        <div class="md:w-1/2 px-3">
                            <label for="date" class="block uppercase tracking-wide text-grey-darker text-xs font-bold mb-2">Muddati</label>
                            <input type="date" name="date" id="date" placeholder="04/11/2021" class="w-full px-3 py-2 placeholder-gray-300 border border-gray-300 rounded-md focus:outline-none focus:ring focus:ring-indigo-100 focus:border-indigo-300 dark:bg-gray-700 dark:text-white dark:placeholder-gray-500 dark:border-gray-600 dark:focus:ring-gray-900 dark:focus:border-gray-500" />
                        </div>
                      </form>

                      <div class="flex justify-center">
                        <button v-show="showBandButton" @click="addBosqich" class="border border-gray-600 focus:outline-none hover:bg-gray-50 mt-3 px-5 py-1 rounded-md text-gray-600 text-sm w-64">
                          bosqich qo'shish
                        </button>
                      </div>

                      <div class="flex items-center mt-4">
                        <button type="submit" class="w-full h-10 bg-indigo-500 focus:outline-none font-medium hover:bg-indigo-600 hover:shadow-lg inline-block leading-6 ml-5 nuxt-link-active pl-8 pr-8 px-6 py-2 ripple rounded shadow text-center text-white text-xs transition uppercase waves-effect">
                          qo'shish
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

<!--   new ilovas           -->
              <form v-for="newIlova in newIlovas" @submit.prevent="createNewIlova">
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
                    <button v-show="newIlovaCreated" type="submit" class="h-10 bg-indigo-500 focus:outline-none font-medium hover:bg-indigo-600 hover:shadow-lg inline-block leading-6 ml-5 nuxt-link-active pl-8 pr-8 px-6 py-2 ripple rounded shadow text-center text-white text-xs transition uppercase waves-effect">
                      Qo'shish</button>
                  </div>
                </div>
              </form>


<!--              <div class="flex flex-col">-->
<!--                <form v-for="newBand in newBands" @submit.prevent="createBand" class="flex justify-end">-->
<!--                  <div class="-mx-3 border border-gray-200 mb-6 md:flex p-8 rounded rounded-lg shadow-md">-->
<!--                    <div class="md:w-1/2 px-3">-->
<!--                      <label class="block uppercase tracking-wide text-grey-darker text-xs font-bold mb-2" for="grid-last-name">-->
<!--                        Soni-->
<!--                      </label>-->
<!--                      <input name="ilova-number" class="appearance-none block w-full bg-grey-lighter text-grey-darker border border-grey-lighter rounded py-3 px-4" id="grid-last-name" type="text">-->
<!--                    </div>-->
<!--                    <div class="md:w-1/2 px-3 mb-6 md:mb-0">-->
<!--                      <label class="block uppercase tracking-wide text-grey-darker text-xs font-bold mb-2" for="grid-first-name">-->
<!--                        Nomi-->
<!--                      </label>-->
<!--                      <input name="ilova-name" class="appearance-none block w-full bg-grey-lighter text-grey-darker border border-red rounded py-3 px-4 mb-3" id="grid-first-name" type="text" >-->
<!--                    </div>-->
<!--                    <div class="flex items-center">-->
<!--                      <button type="submit" class="h-10 bg-indigo-500 focus:outline-none font-medium hover:bg-indigo-600 hover:shadow-lg inline-block leading-6 ml-5 nuxt-link-active pl-8 pr-8 px-6 py-2 ripple rounded shadow text-center text-white text-xs transition uppercase waves-effect">-->
<!--                        qo'shish-->
<!--                      </button>-->
<!--                    </div>-->
<!--                  </div>-->
<!--                </form>-->
<!--                <div class="flex justify-end">-->
<!--                <button v-show="showNewBandButton" @click="addNewBand" class="border border-gray-600 focus:outline-none hover:bg-gray-50 mb-5 mr-52 px-5 py-2.5 rounded-md text-gray-600 text-sm w-64">-->
<!--                  band qo'shish-->
<!--                </button>-->
<!--                </div>-->
<!--              </div>-->

              <div class="flex flex-col">
                  <form v-for="newBand in newBands" @submit.prevent="createBand" class="flex justify-end">
                    <div class="-mx-3 border border-gray-200 mb-6 p-8 rounded rounded-lg shadow-md">

                      <div class="flex">
                        <div class="md:w-1/2 px-3">
                          <label class="block uppercase tracking-wide text-grey-darker text-xs font-bold mb-2" for="grid-last-name">
                            Band Soni
                          </label>
                          <input name="ilova-number" class="appearance-none block w-full bg-grey-lighter text-grey-darker border border-grey-lighter rounded py-3 px-4" id="grid-last-name" type="text">
                        </div>
                        <div class="md:w-1/2 px-3 mb-6 md:mb-0">
                          <label class="block uppercase tracking-wide text-grey-darker text-xs font-bold mb-2" for="grid-first-name">
                            Topshiriq
                          </label>
                          <input name="ilova-name" class="appearance-none block w-full bg-grey-lighter text-grey-darker border border-red rounded py-3 px-4 mb-3" id="grid-first-name" type="text" >
                        </div>
                      </div>

                      <div class="flex">
                        <div class="md:w-1/2 px-3">
                          <label class="block uppercase tracking-wide text-grey-darker text-xs font-bold mb-2" for="grid-state">
                            Mas'ul Viloyat
                          </label>
                          <div class="flex items-center justify-end relative">
                            <select class="block appearance-none w-full bg-grey-lighter border border-grey-lighter text-grey-darker py-3 px-4 pr-8 rounded" id="grid-state">
                              <option>Andijon</option>
                              <option>Buxoro</option>
                              <option>Namangan</option>
                              <option>Farg'ona</option>
                            </select>
                            <div class="pointer-events-none absolute pin-y pin-r flex items-center px-2 text-grey-darker">
                              <svg class="h-4 w-4" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 20 20"><path d="M9.293 12.95l.707.707L15.657 8l-1.414-1.414L10 10.828 5.757 6.586 4.343 8z"/></svg>
                            </div>
                          </div>
                        </div>
                        <div class="md:w-1/2 px-3">
                          <label class="block uppercase tracking-wide text-grey-darker text-xs font-bold mb-2" for="grid-state">
                            Mas'ul Tuman
                          </label>
                          <div class="flex items-center justify-end relative">
                            <select class="block appearance-none w-full bg-grey-lighter border border-grey-lighter text-grey-darker py-3 px-4 pr-8 rounded" id="grid-state">
                              <option>Denov</option>
                              <option>Chinoz</option>
                              <option>Chust</option>
                              <option>Asaka</option>
                            </select>
                            <div class="pointer-events-none absolute pin-y pin-r flex items-center px-2 text-grey-darker">
                              <svg class="h-4 w-4" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 20 20"><path d="M9.293 12.95l.707.707L15.657 8l-1.414-1.414L10 10.828 5.757 6.586 4.343 8z"/></svg>
                            </div>
                          </div>
                        </div>
                      </div>

                      <div class="flex mt-3">
                        <div class="md:w-1/2 px-3">
                          <label class="block uppercase tracking-wide text-grey-darker text-xs font-bold mb-2" for="grid-state">
                            Mas'ul Organ
                          </label>
                          <div class="flex items-center justify-end relative">
                            <select class="block appearance-none w-full bg-grey-lighter border border-grey-lighter text-grey-darker py-3 px-4 pr-8 rounded" id="grid-state">
                              <option>Iqtisodiyot vazirligi</option>
                              <option>Moliya vazirligi</option>
                              <option>Davlat statistika qo‘mitasi</option>
                              <option>Intellektual mulk agentligi</option>
                            </select>
                            <div class="pointer-events-none absolute pin-y pin-r flex items-center px-2 text-grey-darker">
                              <svg class="h-4 w-4" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 20 20"><path d="M9.293 12.95l.707.707L15.657 8l-1.414-1.414L10 10.828 5.757 6.586 4.343 8z"/></svg>
                            </div>
                          </div>
                        </div>
                        <div class="md:w-1/2 px-3">
                            <label for="date" class="block uppercase tracking-wide text-grey-darker text-xs font-bold mb-2">Muddati</label>
                            <input type="date" name="date" id="date" placeholder="04/11/2021" class="w-full px-3 py-2 placeholder-gray-300 border border-gray-300 rounded-md focus:outline-none focus:ring focus:ring-indigo-100 focus:border-indigo-300 dark:bg-gray-700 dark:text-white dark:placeholder-gray-500 dark:border-gray-600 dark:focus:ring-gray-900 dark:focus:border-gray-500" />
                        </div>
                      </div>

                      <form v-for="newBosqich in newBosqichs" class="bg-gray-100 border flex ml-20 mt-5 p-2 py-3 rounded rounded-md">
                        <div class="border border-gray-300 flex font-black items-center p-2">1</div>
                        <div class="md:w-1/2 px-3">
                          <label class="block uppercase tracking-wide text-grey-darker text-xs font-bold mb-2" for="grid-last-name">
                            Nomi
                          </label>
                          <input name="ilova-number" class="appearance-none block w-full bg-grey-lighter text-grey-darker border border-grey-lighter rounded py-3 px-4" id="grid-last-name" type="text">
                        </div>
                        <div class="md:w-1/2 px-3">
                            <label for="date" class="block uppercase tracking-wide text-grey-darker text-xs font-bold mb-2">Muddati</label>
                            <input type="date" name="date" id="date" placeholder="04/11/2021" class="w-full px-3 py-2 placeholder-gray-300 border border-gray-300 rounded-md focus:outline-none focus:ring focus:ring-indigo-100 focus:border-indigo-300 dark:bg-gray-700 dark:text-white dark:placeholder-gray-500 dark:border-gray-600 dark:focus:ring-gray-900 dark:focus:border-gray-500" />
                        </div>
                      </form>

                      <div class="flex justify-center">
                        <button v-show="showBandButton" @click="addNewBosqich" class="border border-gray-600 focus:outline-none hover:bg-gray-50 mt-3 px-5 py-1 rounded-md text-gray-600 text-sm w-64">
                          bosqich qo'shish
                        </button>
                      </div>

                      <div class="flex items-center mt-4">
                        <button type="submit" class="w-full h-10 bg-indigo-500 focus:outline-none font-medium hover:bg-indigo-600 hover:shadow-lg inline-block leading-6 ml-5 nuxt-link-active pl-8 pr-8 px-6 py-2 ripple rounded shadow text-center text-white text-xs transition uppercase waves-effect">
                          qo'shish
                        </button>
                      </div>
                    </div>
                  </form>
                  <div class="flex justify-end">
                  <button v-show="showNewBandButton" @click="addNewBand" class="border border-gray-600 focus:outline-none hover:bg-gray-50 mb-5 mr-52 px-5 py-2.5 rounded-md text-gray-600 text-sm w-64">
                    band qo'shish
                  </button>
                  </div>
                </div>

              <!--   end new ilovas           -->


          <button @click="addNewIlova" class="focus:outline-none text-gray-600 text-sm py-2.5 px-5 rounded-md border border-gray-600 hover:bg-gray-50">
            yangi ilova
          </button>
            </div>
        </v-tab>

        <v-tab title="Farmonga Band qo'shish">
          <div class="bg-white shadow-md rounded px-8 pt-6 pb-8 mb-4 flex flex-col my-2">
            <div class="-mx-3 md:flex mb-6">
              <div class="md:w-1/2 px-3 mb-6 md:mb-0">
                <label class="block uppercase tracking-wide text-grey-darker text-xs font-bold mb-2" for="grid-first-name">
                  Band Soni
                </label>
                <input class="appearance-none block w-full bg-grey-lighter text-grey-darker border border-red rounded py-3 px-4 mb-3" id="grid-first-name" type="text">
              </div>
              <div class="md:w-1/2 px-3">
                <label class="block uppercase tracking-wide text-grey-darker text-xs font-bold mb-2" for="grid-last-name">
                  Topshiriq
                </label>
                <input class="appearance-none block w-full bg-grey-lighter text-grey-darker border border-grey-lighter rounded py-3 px-4" id="grid-last-name" type="text">
              </div>
            </div>
            <div class="-mx-3 md:flex mb-6">
              <div class="md:w-full px-3">
                <label for="date" class="block uppercase tracking-wide text-grey-darker text-xs font-bold mb-2">Muddati</label>
                <input type="date" name="date" id="date" placeholder="04/11/2021" class="w-full px-3 py-2 placeholder-gray-300 border border-gray-300 rounded-md focus:outline-none focus:ring focus:ring-indigo-100 focus:border-indigo-300 dark:bg-gray-700 dark:text-white dark:placeholder-gray-500 dark:border-gray-600 dark:focus:ring-gray-900 dark:focus:border-gray-500" />
              </div>
            </div>
            <div class="-mx-3 md:flex mb-2">
              <div class="md:w-1/2 px-3 mb-6 md:mb-0">
                <label class="block uppercase tracking-wide text-grey-darker text-xs font-bold mb-2" for="grid-state">
                  Mas'ul Viloyat
                </label>
                <div class="flex items-center justify-end relative">
                  <select class="block appearance-none w-full bg-grey-lighter border border-grey-lighter text-grey-darker py-3 px-4 pr-8 rounded" id="grid-state">
                    <option>Andijon</option>
                    <option>Buxoro</option>
                    <option>Namangan</option>
                    <option>Farg'ona</option>
                  </select>
                  <div class="pointer-events-none absolute pin-y pin-r flex items-center px-2 text-grey-darker">
                    <svg class="h-4 w-4" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 20 20"><path d="M9.293 12.95l.707.707L15.657 8l-1.414-1.414L10 10.828 5.757 6.586 4.343 8z"/></svg>
                  </div>
                </div>
              </div>
              <div class="md:w-1/2 px-3 mb-6 md:mb-0">
                <label class="block uppercase tracking-wide text-grey-darker text-xs font-bold mb-2" for="grid-state">
                  Mas'ul Tuman
                </label>
                <div class="flex items-center justify-end relative">
                  <select class="block appearance-none w-full bg-grey-lighter border border-grey-lighter text-grey-darker py-3 px-4 pr-8 rounded" id="grid-state">
                    <option>Denov</option>
                    <option>Chinoz</option>
                    <option>Chust</option>
                    <option>Asaka</option>
                  </select>
                  <div class="pointer-events-none absolute pin-y pin-r flex items-center px-2 text-grey-darker">
                    <svg class="h-4 w-4" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 20 20"><path d="M9.293 12.95l.707.707L15.657 8l-1.414-1.414L10 10.828 5.757 6.586 4.343 8z"/></svg>
                  </div>
                </div>
              </div>
              <div class="md:w-1/2 px-3 mb-6 md:mb-0">
                <label class="block uppercase tracking-wide text-grey-darker text-xs font-bold mb-2" for="grid-state">
                  Mas'ul Organ
                </label>
                <div class="flex items-center justify-end relative">
                  <select class="block appearance-none w-full bg-grey-lighter border border-grey-lighter text-grey-darker py-3 px-4 pr-8 rounded" id="grid-state">
                    <option>Iqtisodiyot vazirligi</option>
                    <option>Moliya vazirligi</option>
                    <option>Davlat statistika qo‘mitasi</option>
                    <option>Intellektual mulk agentligi</option>
                  </select>
                  <div class="pointer-events-none absolute pin-y pin-r flex items-center px-2 text-grey-darker">
                    <svg class="h-4 w-4" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 20 20"><path d="M9.293 12.95l.707.707L15.657 8l-1.414-1.414L10 10.828 5.757 6.586 4.343 8z"/></svg>
                  </div>
                </div>
              </div>
            </div>
          </div>

          <form v-for="farmonBosqich in farmonBosqichs" @submit.prevent="" class="bg-white flex flex-col mb-4 ml-48 my-2 pt-6 px-8 rounded shadow-md">
            <div class="-mx-3 md:flex mb-6">
              <div class="md:w-1/2 px-3 mb-6 md:mb-0">
                <label class="block uppercase tracking-wide text-grey-darker text-xs font-bold mb-2" for="grid-first-name">
                  Nomi
                </label>
                <input class="appearance-none block w-full bg-grey-lighter text-grey-darker border border-red rounded py-3 px-4 mb-3" id="grid-first-name" type="text">
              </div>
              <div class="md:w-1/2 px-3">
                <label for="date" class="block uppercase tracking-wide text-grey-darker text-xs font-bold mb-2">Muddati</label>
                <input type="date" name="date" id="date" placeholder="04/11/2021" class="w-full px-3 py-2 placeholder-gray-300 border border-gray-300 rounded-md focus:outline-none focus:ring focus:ring-indigo-100 focus:border-indigo-300 dark:bg-gray-700 dark:text-white dark:placeholder-gray-500 dark:border-gray-600 dark:focus:ring-gray-900 dark:focus:border-gray-500" />
              </div>
              <div class="flex px-3">
<!--                <label for="date" class="block uppercase tracking-wide text-grey-darker text-xs font-bold mb-2">Muddati</label>-->
<!--                <input type="date" name="date" id="date" placeholder="04/11/2021" class="w-full px-3 py-2 placeholder-gray-300 border border-gray-300 rounded-md focus:outline-none focus:ring focus:ring-indigo-100 focus:border-indigo-300 dark:bg-gray-700 dark:text-white dark:placeholder-gray-500 dark:border-gray-600 dark:focus:ring-gray-900 dark:focus:border-gray-500" />-->
                <div class="flex items-center">
                    <button v-show="ilovaCreated" class="h-10 bg-indigo-500 focus:outline-none font-medium hover:bg-indigo-600 hover:shadow-lg inline-block leading-6 ml-5 nuxt-link-active pl-8 pr-8 px-6 py-2 ripple rounded shadow text-center text-white text-xs transition uppercase waves-effect">
                      Qo'shish</button>
                  </div>
              </div>
            </div>
          </form>

          <div class="flex flex-col mb-4 ml-48 my-2 px-8 rounded">
            <div class="flex justify-center">
              <button @click="addFarmonBosqich" class="border border-gray-600 focus:outline-none hover:bg-gray-50 mt-3 px-5 py-1 rounded-md text-gray-600 text-sm w-64">
                bosqich qo'shish
              </button>
            </div>
          </div>

          <div class="bg-indigo-500 flex flex-col my-2 pb-8 pt-6 px-8 rounded shadow-md">
            <button class="font-bold text-white">Farmon qo'shish</button>
          </div>

        </v-tab>
    </vue-tabs>

  </div>
</template>

<script>
export default {
  data() {
    return {
      ilovas: {
        bands: []
      },
      bands: [],
      newIlovas: [],
      newBands: [],
      showBandButton: false,
      showNewBandButton: false,
      ilovaCreated: true,
      newIlovaCreated: true,
      bosqichs: [],
      newBosqichs: [],

      // farmonBands: [1],
      farmonBosqichs: [],
    }
  },
  methods: {
    createIlova(){
      this.showBandButton = true
      this.ilovaCreated = false
      return 'created'
    },
    createNewIlova(){
      this.showNewBandButton = true
      this.newIlovaCreated = false
      return 'created'
    },
    addIlova(){
      this.newIlovas.push(1)
    },
    addNewIlova(){
      this.newIlovas.push(1)
      if (this.ilovas >= 1){
        this.showBandButton = false
      }
    },
    createBand(){
      return 'asdf'
    },
    addBand(){
        this.bands.push(1)
    },
    addNewBand(){
        this.newBands.push(1)
    },
    addBosqich(){
      this.bosqichs.push(1)
      return 'asfd'
    },
    addNewBosqich(){
      this.newBosqichs.push(1)
      return 'asfd'
    },
    addFarmonBosqich(){
      this.farmonBosqichs.push(1)
      return 'asdf'
    }
  }
}
</script>
