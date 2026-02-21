<script setup>
</script>

<template>
   <!-- nav bar -->
    <nav>
        <div class="flex justify-end gap-8 px-8 p-3 font-sans ">
            <a href="" class="hover:text-gray-700">Vector</a>
            <a href="" class="hover:text-gray-700" >IIIustrations</a>
            <a href="" class="hover:text-gray-700">Images</a>
            <a href="" class="hover:text-gray-700">Icons</a>
        </div>
    </nav>

    
    <div class="flex justify-between pt-6 px-8" >
        <!-- search -->
        <div class="font-sans relative ">
            <input type="text" placeholder="Search" class="border border-gray-300 w-72 rounded-2xl px-2 py-3 shadow-md">
           <div class="absolute inset-y-0 right-5 mb-3 flex items-center">
                <svg class="w-5 h-5 text-gray-400" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24"
                    stroke="currentColor" stroke-width="2">
                    <circle cx="11" cy="11" r="8" />
                    <line x1="21" y1="21" x2="16.65" y2="16.65" />
                </svg>
            </div>
        </div>
        <!-- upload button -->
        <div class="font-sans">
            <button class="bg-black text-white text-lg px-10 py-4 rounded-xl hover:bg-gray-700 cursor-pointer">Upload</button>
        </div>
    </div>

    <!-- images -->
     <div class="grid grid-cols-3 gap-5 p-10">
        <img src="../assets/1.jpg" alt="image1" class="w-full h-60 object-cover rounded-xs">
        <img src="../assets/2.jpg" alt="image2" class="w-full h-60 object-cover rounded-xs">
        <img src="../assets/3.jpg" alt="image3" class="w-full h-60 object-cover rounded-xs">
        <img src="../assets/4.jpg" alt="image4" class="w-full h-60 object-cover rounded-xs">
        <img src="../assets/5.jpg" alt="image5" class="w-full h-60 object-cover rounded-xs">
        <img src="../assets/6.jpg" alt="image6" class="w-full h-60 object-cover rounded-xs">
     </div>
</template>

<style scoped></style>
