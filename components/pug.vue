<template lang="pug">
div.flex.flex-col.h-screen.justify-center.bg-no-repeat.bg-cover(style="background-image:url(login.jpeg)")
    div.mx-auto.border-2.h-80.w-80.rounded-xl.bg-gradient-to-r.from-sky-500.to-indigo-500
        h1.text-center.font-serif.text-3xl.mt-7 LOGIN
            div
                div.flex.items-center.justify-center.mb-7.mt-8
                    input.border-solid.border-2.w-48.text-sm(type="text" placeholder="Enter Your Email")
                    MdiIcon(icon="mdiAccount" class="relative right-7 text-base")
    
                div.flex.items-center.justify-center.mb-9
                    input.border-solid.border-2.w-48.text-sm(type="password" placeholder="Enter Passwords")
                    MdiIcon(icon="mdiLock" class="relative right-7 text-base")
                button(type="submit" class="border-2 bg-green-500 flex relative left-28 py-1 px-5 rounded-md mb-4 text-sm") Login

                div.mb-1.flex.items-center.justify-center
                    input(type="checkbox" class="mr-2")
                    label.text-sm.mr-8 Remember me
                    label.text-sm Forgot Password?
</template>
    
    