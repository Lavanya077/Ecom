<template lang="pug">
div.container
    button.adduser(@click="navigateToForm") Add User
    table.table
        thead
            tr
                th ID
                th Name
                th Email
                th Actions
        tbody
            tr(v-for="(user, index) in formData" :key="index")
                td {{ user.id }}
                td {{ user.name }}
                td {{ user.email }}
                td
                    button.but(@click="deleteUser(index)") Delete
</template>

<script setup>
import { ref, onMounted } from 'vue'
import { useRouter } from 'vue-router'

const formData = ref([])

onMounted(() => {
    const storedData = localStorage.getItem('formData')
    if (storedData) {
        formData.value = JSON.parse(storedData)
    }
    console.log("Retrieved Data:", formData.value)
})

const router = useRouter()

const navigateToForm = () => {
    router.push('/form')
}

const deleteUser = (index) => {
    formData.value.splice(index, 1)
    localStorage.setItem('formData', JSON.stringify(formData.value))
}
</script>

<style>
.container {
    @apply flex mx-auto h-screen justify-center items-center;
}
tr, td, th {
    @apply border-2 p-2;
}
.but {
    @apply bg-red-500 p-1 rounded-md;
}
.adduser {
    @apply mb-4 bg-blue-500 p-2 rounded-md;
}
</style>
