<template lang="pug">
div.container
    label Id 
    input.int(type="text" v-model="form.id" placeholder="Enter your ID")
    label Name 
    input.int(type="text" v-model="form.name" placeholder="Enter your Name")
    label Email
    input.int(type="text" v-model="form.email" placeholder="Enter your Email")
    button.subbut(type="button" @click="submitForm") SUBMIT
</template>

<script setup>
import { ref } from 'vue'
import { useRouter } from 'vue-router'

const form = ref({
    id: '',
    name: '',
    email: ''
})

const router = useRouter()
const submitForm = () => {
let users = JSON.parse(localStorage.getItem('formData')) || [];
if (!Array.isArray(users)) {
    users = [];
}
users.push({ ...form.value });
localStorage.setItem('formData', JSON.stringify(users));
router.push('/table');
}

</script>

<style>
.container {
    @apply flex flex-col h-screen justify-center items-center border-2;
}
.int {
    @apply border-b-4 mb-4;
}
label {
    @apply text-xl mb-2;
}
.subbut {
    @apply bg-green-500 p-1 rounded-md;
}
</style>
