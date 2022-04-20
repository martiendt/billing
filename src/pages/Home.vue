<script setup>
import welcome from '@/components/welcome.vue'
import { computed } from 'vue';
import { useHead } from '@vueuse/head'
import { ref } from "vue"

useHead({
  // Can be static or computed
  title: computed(() => "title"),
  meta: [
    {
      name: `description`,
      content: computed(() => "description"),
    },
  ],
})
</script>

<template>
<main class="h-full overflow-y-auto">
  <div class="container px-6 mx-auto grid">
    <h2
      class="my-6 text-2xl font-semibold text-gray-700 dark:text-gray-200"
    >
      Dashboard
    </h2>
    <!-- CTA -->
    <a
      class="flex items-center justify-between p-4 mb-8 text-sm font-semibold text-purple-100 bg-red-600 rounded-lg shadow-md focus:outline-none focus:shadow-outline-purple"
      href="https://github.com/estevanmaito/windmill-dashboard"
    >
      <div class="flex items-center">
        <svg
          class="w-5 h-5 mr-2"
          fill="currentColor"
          viewBox="0 0 20 20"
        >
          <path
            d="M9.049 2.927c.3-.921 1.603-.921 1.902 0l1.07 3.292a1 1 0 00.95.69h3.462c.969 0 1.371 1.24.588 1.81l-2.8 2.034a1 1 0 00-.364 1.118l1.07 3.292c.3.921-.755 1.688-1.54 1.118l-2.8-2.034a1 1 0 00-1.175 0l-2.8 2.034c-.784.57-1.838-.197-1.539-1.118l1.07-3.292a1 1 0 00-.364-1.118L2.98 8.72c-.783-.57-.38-1.81.588-1.81h3.461a1 1 0 00.951-.69l1.07-3.292z"
          ></path>
        </svg>
        <span class="uppercase">You have unpaid invoice Rp 1.000.000</span>
      </div>
      <span>Pay now &RightArrow;</span>
    </a>
    <!-- Cards -->
    <div class="grid gap-6 mb-8 md:grid-cols-2 xl:grid-cols-4">
      <!-- Card -->
      <div
        class="flex items-center p-4 bg-white rounded-lg shadow-xs dark:bg-gray-800"
      >
        <div
          class="p-3 mr-4 text-red-700 bg-red-200 rounded-full dark:text-orange-100 dark:bg-orange-500"
        >
          <svg class="w-5 h-5" fill="currentColor" viewBox="0 0 20 20">
            <path
              d="M13 6a3 3 0 11-6 0 3 3 0 016 0zM18 8a2 2 0 11-4 0 2 2 0 014 0zM14 15a4 4 0 00-8 0v3h8v-3zM6 8a2 2 0 11-4 0 2 2 0 014 0zM16 18v-3a5.972 5.972 0 00-.75-2.906A3.005 3.005 0 0119 15v3h-3zM4.75 12.094A5.973 5.973 0 004 15v3H1v-3a3 3 0 013.75-2.906z"
            ></path>
          </svg>
        </div>
        <div>
          <p
            class="mb-2 text-sm font-medium text-gray-600 dark:text-gray-400"
          >
            Unpaid Invoice
          </p>
          <p
            class="text-2xl font-semibold text-gray-700 dark:text-gray-200"
          >
            Rp. 1.000.000
          </p>
        </div>
      </div>
      <!-- Card -->
      <div
        class="flex items-center p-4 bg-white rounded-lg shadow-xs dark:bg-gray-800"
      >
        <div
          class="p-3 mr-4 text-green-700 bg-green-200 rounded-full dark:text-green-100 dark:bg-green-500"
        >
          <svg class="w-5 h-5" fill="currentColor" viewBox="0 0 20 20">
            <path
              fill-rule="evenodd"
              d="M4 4a2 2 0 00-2 2v4a2 2 0 002 2V6h10a2 2 0 00-2-2H4zm2 6a2 2 0 012-2h8a2 2 0 012 2v4a2 2 0 01-2 2H8a2 2 0 01-2-2v-4zm6 4a2 2 0 100-4 2 2 0 000 4z"
              clip-rule="evenodd"
            ></path>
          </svg>
        </div>
        <div class="relative w-full">
          <p
            class="mb-2 text-sm font-medium text-gray-600 dark:text-gray-400"
          >
            Account balance
          </p>
          <p
            class="text-lg font-semibold text-gray-700 dark:text-gray-200"
          >
            Rp 0
          </p>
          <span
            class="absolute cursor-pointer text-xs right-0 top-0 px-2 py-1 font-semibold leading-tight text-blue-500  rounded dark:bg-green-700 dark:text-green-100"
          >
            + Topup
          </span>
        </div>
      </div>
    </div>

    <!-- New Table -->
    <div class="w-full overflow-hidden rounded-lg shadow-xs">
      <div class="w-full overflow-x-auto">
        <table class="w-full whitespace-no-wrap">
          <thead>
            <tr
              class="text-xs font-semibold tracking-wide text-left text-gray-500 uppercase border-b dark:border-gray-700 bg-gray-50 dark:text-gray-400 dark:bg-gray-800"
            >
              <th class="px-4 py-3">Invoice Number</th>
              <th class="px-4 py-3">Project Name</th>
              <th class="px-4 py-3">Due Date</th>
              <th class="px-4 py-3">Total Amount</th>
              <th class="px-4 py-3">Payment Status</th>
              <th class="px-4 py-3"></th>
            </tr>
          </thead>
          <tbody
            class="bg-white divide-y dark:divide-gray-700 dark:bg-gray-800"
          >
            <tr class="text-gray-700 dark:text-gray-400">
              <td class="px-4 py-3">
                <div class="flex items-center text-sm">
                  <div>
                    <p class="font-semibold">INVOICE #202220301</p>
                  </div>
                </div>
              </td>
              <td class="px-4 py-3 text-sm">
                <div class="flex items-center text-sm">
                  <div>
                    <p class="font-semibold">Point ERP</p>
                    <p class="text-xs text-gray-600 dark:text-gray-400">
                      Rp. 500.000
                    </p>
                  </div>
                </div>
              </td>
              <td class="px-4 py-3 text-sm">
                01/04/2022
              </td>
              <td class="px-4 py-3 text-sm">
                500.000
              </td>
              <td class="px-4 py-3 text-xs">
                <span
                  class="px-2 py-1 font-semibold leading-tight text-green-700 bg-gray-100 rounded-full dark:bg-green-700 dark:text-green-100"
                >
                  Unpaid
                </span>
              </td>
              <td class="px-4 py-3 text-xs space-x-3 text-right">
                <span
                  class="cursor-pointer px-2 py-1 font-semibold leading-tight text-blue-100 bg-blue-500 rounded dark:bg-green-700 dark:text-green-100"
                >
                  Pay Invoice
                </span>
                <span
                  class="cursor-pointer px-2 py-1 font-semibold leading-tight text-orange-100 bg-orange-500 rounded dark:bg-green-700 dark:text-green-100"
                >
                  Print
                </span>
              </td>
            </tr>
            <tr class="text-gray-700 dark:text-gray-400">
              <td class="px-4 py-3">
                <div class="flex items-center text-sm">
                  <div>
                    <p class="font-semibold">INVOICE #202220201</p>
                  </div>
                </div>
              </td>
              <td class="px-4 py-3 text-sm">
                <div class="flex items-center text-sm">
                  <div>
                    <p class="font-semibold">Point ERP</p>
                    <p class="text-xs text-gray-600 dark:text-gray-400">
                      Rp. 500.000
                    </p>
                  </div>
                </div>
              </td>
              <td class="px-4 py-3 text-sm">
                01/04/2022
              </td>
              <td class="px-4 py-3 text-sm">
                500.000
              </td>
              <td class="px-4 py-3 text-xs">
                <span
                  class="px-2 py-1 font-semibold leading-tight text-green-700 bg-gray-100 rounded-full dark:bg-green-700 dark:text-green-100"
                >
                  Unpaid
                </span>
              </td>
              <td class="px-4 py-3 text-xs space-x-3 text-right">
                <span
                  class="cursor-pointer px-2 py-1 font-semibold leading-tight text-blue-100 bg-blue-500 rounded dark:bg-green-700 dark:text-green-100"
                >
                  Pay Invoice
                </span>
                <span
                  class="cursor-pointer px-2 py-1 font-semibold leading-tight text-orange-100 bg-orange-500 rounded dark:bg-green-700 dark:text-green-100"
                >
                  Print
                </span>
              </td>
            </tr>
          </tbody>
        </table>
      </div>
    </div>
  </div>
</main>
</template>
