<script setup>

const loading =  ref(false);

const form = ref({
    email: "majadul.dev@gmail.com",
    password: "12345678"
});

async function handleLogin() {

    loading.value = true;    
    
}

</script>

<template>
    <div>
        
        <div v-if="loading" class="min-h-screen w-full bg-black bg-opacity-[.3] flex items-center fixed">
            <div class="w-12 mx-auto"><img alt="loading..." src="/spinner.gif"></div>
        </div>
        

        <div class="min-h-screen bg-gray-100 fixed w-full -z-50">
        <div class="place-content-center">
            <div class="p-3 mt-12 w-24 mx-auto"><img alt="logo" src="/logo.png"></div>
            
        </div>

        
            <div class="w-80 bg-white shadow-lg rounded-lg p-4 mx-auto bg-opacity-75">
                <h5 class="mb-2 text-2xl font-bold tracking-tight text-center text-gray-900 dark:text-white">Login</h5>
                <form @submit.prevent="handleLogin">
                    <label class="block mt-2"><span class="block text-sm font-medium text-slate-700">Email</span>
                        <input v-model="form.email" type="text" name="email" placeholder="email here" autocomplete="true" class="mt-1 block w-full px-3 py-1 focus:outline-none bg-white border border-slate-300 rounded-md text-sm focus:border-gray-500">
                    </label>
                    
                    <label class="block mt-2"><span class="block text-sm font-medium text-slate-700">Password</span>
                        <input  v-model="form.password" type="password" name="password"  class="mt-1 block w-full px-3 py-1 focus:outline-none bg-white border border-slate-300 rounded-md text-sm focus:border-gray-500 ">
                    </label>

                    <button type="submit" class="px-3 mt-4 mb-4 py-3 w-full text-sm font-medium text-center text-white bg-red-700 rounded-lg hover:bg-red-600 focus:outline-none">Login</button>
                </form>
                <div class="mt-4 text-center"><a class="text-sm text-blue-900" >Forgot Password?</a></div>

            </div>
        
            <img class="background" src="/landscape.svg" />
        
    </div>
    </div>
</template>

<style>

    .background {

        position: absolute;
        bottom: 0;
        z-index: -1;
    }
</style>