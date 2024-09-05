<template>
    <div class="flex  flex-col h-screen justify-center  bg-no-repeat bg-cover" style="background-image:url(login.jpeg)">
        <div class="  absolute left-3/4 border-2 h-80 w-80 rounded-xl bg-gradient-to-r from-sky-500 to-indigo-500 ">
        <h1  class="text-center font-serif text-4xl py-8">LOGIN</h1>
        <div class="">
            <div class="flex items-center justify-center mb-7">
                <input class="border-solid border-2 w-48" type="text" placeholder="Enter Your Email"  />
                <MdiIcon icon="mdiAccount" class="relative right-7 text-xl items-center"   />
            </div>
            <div class="flex items-center justify-center mb-5">
                <input class="border-solid border-2 w-48" type="password" placeholder="Enter Passwords"/>
                <MdiIcon icon="mdiLock"  class="relative right-7 text-xl items-center"  />
            </div>
            <NuxtLink to="/form"><button type="submit"class="border-2 bg-green-500 flex  relative left-32 py-1  px-5 rounded-md mb-3" >Login</button></NuxtLink>
            <div class="mb-1">
                <input type="checkbox" class="mr-2 ml-5">
                <label class="mr-8">Remember me</label>
                <label class="">Forgot Password?</label>
            </div>
        </div>
        </div>
    </div>
</template>


<!-- <script>
export default {
    methods:{
        tableB(){
            this.$router.push('/table')
        }
    }        >
}
</script> -->