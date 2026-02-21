<script setup>
const contents = [
  {
    name: "BASIC",
    storage: "100GB",
    price: "$1.99/month",
    features: [
      "100 GB storage",
      "Option to add members",
      "Extra member benefits"
    ]
  },
  {
    name: "STANDARD",
    storage: "200GB",
    price: "$3.99/month",
    features: [
    "200 GB storage",
      "Option to add members",
      "Extra member benefits"
    ]
  },
  {
    name: "PREMIUM",
    storage: "2TB",
    price: "$8.99/month",
    features: [
      "2 TB storage",
      "Option to add members",
      "Extra member benefits"
    ]
  }
]
</script>

<template>
   <!-- bg -->
   <div class="bg-blue-950 min-h-screen  flex items-center justify-center">
        <!-- all 3 content -->
        <div class="grid grid-cols-3 text-white gap-10">
            <!-- content basic -->
            <div v-for="content in contents":key="content.name" class="group border-10 border-gray-700 rounded-3xl text-center w-70 mx-auto hover:border-purple-600">
                <p class="p-7 pb-9">{{content.name}}</p>
                <p class="text-4xl font-serif">{{content.storage}}</p>
                <p class="pb-7">{{content.price}}</p>

                <!-- button -->
                <button
                    class="border border-purple-600 text-white text-center w-35 py-3 rounded-lg group-hover:bg-purple-600 cursor-pointer ">Purchase</button>

                <!-- 3 text -->
                <div class="mt-13 border-t-3 border-t-gray-700 pt-8 pb-8">

                  <div v-for="feature in content.features" class="flex justify-center items-center gap-3 pt-2">
                        <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5"
                            stroke="currentColor" class="size-6 text-white">
                            <path stroke-linecap="round" stroke-linejoin="round" d="m4.5 12.75 6 6 9-13.5" />
                        </svg>
                        <p>{{ feature }}</p>
                    </div>
                </div>
          
            </div>
        </div>
    </div>
</template>

<style scoped></style>