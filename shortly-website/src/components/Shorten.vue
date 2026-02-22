<script setup>
import { ref } from 'vue'
const links = ref([
    {
        original: 'https://www.frontendmentor.io',
        short: 'https://rel.ink/k4yK',
        isCopied: false
    },
    {
        original: 'https://twitter.com/frontendmentor',
        short: 'https://rel.ink/gxOXp9',
        isCopied: true
    },
    {
        original: 'https://linkedin.com/frontend-mentor',
        short: 'https://rel.ink/gob3X9',
        isCopied: false
    }
])

const urlInput = ref('')
const errorMsg = ref('')

const handelShorten = () => {
    if (urlInput.value === '') {
        errorMsg.value = `Please add a link`
        return
    }

    errorMsg.value = ''

    links.value.unshift({
        original: urlInput.value,
        short: 'https://rel.ink/' + Math.random().toString(36).substring(7),
        isCopied: false
    })
    urlInput.value = ''
}

const handleCopy = async (link) => {
    try {
        await navigator.clipboard.writeText(link.short)
        links.value.forEach(i => i.isCopied = false)

        link.isCopied = true
    } catch (err) {
        alert('Copy failed')
    }
}


</script>

<template>
    <div class="pt-16 px-5 bg-gray-50 ">
        <!-- input link -->
        <div class="flex flex-col items-center md:flex-row bg-indigo-950 rounded-xl p-12 gap-5">
            <input v-model="urlInput" placeholder="Shorten a link here"
                class="py-2 md:py-3 w-60 md:flex-1 p-2 text-amber-600 bg-white rounded-lg"></input>
            <p v-if="errorMsg" class="text-red-400 text-sm">{{ errorMsg }}</p>
            <button @click="handelShorten" class="text-white bg-cyan-500 py-2 md:py-3 w-60 rounded-lg md:w-auto p-10">Shorten
                it!</button>
        </div>

        <!-- copy links -->
        <div class="flex flex-col gap-5 pt-5 pb-5">
            <div v-for="(link, index) in links" :key="index"
                class="flex flex-col md:flex-row justify-between items-center p-6 rounded-xl bg-white space-y-0.5">
                <p class="text-sm font-bold">{{ link.original }}</p>
                <div class="flex flex-col items-center md:flex-row md:items-center gap-4 md ">
                    <p class="text-sm font-bold text-cyan-500 pb-2">{{ link.short }}</p>
                    <button @click="handleCopy(link)" :class="link.isCopied ? 'bg-indigo-950' : 'bg-cyan-500'"
                        class="text-white bg-cyan-500 py-2 w-25 rounded-lg">Copy</button>
                </div>
            </div>
        </div>
    </div>



</template>

<style scoped></style>