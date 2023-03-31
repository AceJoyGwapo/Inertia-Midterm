<script setup>
import {useForm, Link} from '@inertiajs/inertia-vue3'
let form = useForm({
    'username': '',
    'password': ''
})
let submit = () => {
    form.post('/')
}
</script>

<template layout="default">
    <div class="bg-gradient-to-tr from-indigo-600 via-sky-600 to-teal-400">
        <div class="flex h-full py-48">
          <div class="w-1/2 mx-auto rounded-lg shadow bg-gray-50 sm:max-w-md xl:p-0">
              <div class="p-6 space-y-4 md:space-y-6 sm:p-8">
                  <h1 class="text-3xl font-bold leading-tight tracking-tight text-center text-gray-900">
                      Log in
                  </h1>
                  <div class="text-sm text-center text-red-500" v-if="form.errors.authentication">{{ form.errors.authentication }}</div>
                  <form class="space-y-4 md:space-y-6" @submit.prevent="submit">
                      <div>
                          <label for="email" class="block mb-2 text-sm font-medium text-gray-900">Username</label>
                          <input v-model="form.username" type="text" id="email" class="bg-gray-50 border border-gray-300 text-gray-900 sm:text-sm rounded-lg focus:ring-primary-600 focus:border-primary-600 block w-full p-2.5">
                          <div class="text-sm italic text-red-500" v-if="form.errors.username">{{ form.errors.username }}</div>
                      </div>
                      <div>
                          <label for="password" class="block mb-2 text-sm font-medium text-gray-900">Password</label>
                          <input v-model="form.password" type="password" name="password" id="password" class="bg-gray-50 border border-gray-300 text-gray-900 sm:text-sm rounded-lg focus:ring-primary-600 focus:border-primary-600 block w-full p-2.5">
                          <div class="text-sm italic text-red-500" v-if="form.errors.password">{{ form.errors.password }}</div>
                      </div>
                      <button type="submit" class="w-full text-white bg-blue-500 focus:ring-4 focus:outline-none focus:ring-primary-300 font-medium rounded-lg text-sm px-5 py-2.5 text-center">Log in</button>
                  </form>
                  <p class="text-sm font-light text-center text-gray-500 ">
                    Don’t have an account? <Link href="/signup" class="font-medium text-primary-600 hover:underline hover:text-blue-600">Create account</Link>
                </p>
              </div>
          </div>
      </div>
    </div>
</template>
