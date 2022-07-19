<template>
    <Head title="Dashboard" />

    <BreezeAuthenticatedLayout>
        <template #header>
            <h2 class="font-semibold text-xl text-gray-800 leading-tight">
                Students
            </h2>
        </template>

        <div class="py-12">
           
            <div class="max-w-7xl mx-auto sm:px-6 lg:px-8">
                <div class="flex justify-start m-2 p-2">
                <Link :href="route('students')" class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded">
                    Go Back
                </Link>
            </div>

            <div class="text-danger">
              
            </div>

<div>
  <div class="md:grid md:grid-cols-3 md:gap-6">
    <div class="md:col-span-1">
      <div class="px-4 sm:px-0">
        <h3 class="text-lg font-medium leading-6 text-gray-900">Create A Student</h3>
        <p class="mt-1 text-sm text-gray-600">
          This information will be displayed publicly so be careful what you share.
        </p>
      </div>
    </div>
    <div class="mt-5 md:mt-0 md:col-span-2">

      <form @submit.prevent="submitForm" method="POST">

        <div class="shadow sm:rounded-md sm:overflow-hidden">
          <div class="px-4 py-5 bg-white space-y-6 sm:p-6">
            <div class="grid grid-cols-3 gap-6">
              <div class="col-span-3 sm:col-span-2">
                <label for="company-website" class="block text-sm font-medium text-gray-700">
                  Name
                </label>
                <div class="mt-1 flex rounded-md shadow-sm">
            
                  <input type="text" name="name" id="company-website" v-model="form.name" class="focus:ring-indigo-500 focus:border-indigo-500 flex-1 block w-full rounded-none rounded-r-md sm:text-sm border-gray-300" placeholder="Your Name Here" required>
                </div>
              </div>
            </div>


               <div class="grid grid-cols-3 gap-6">
              <div class="col-span-3 sm:col-span-2">
                <label for="company-website" class="block text-sm font-medium text-gray-700">
                  Address
                </label>
                <div class="mt-1 flex rounded-md shadow-sm">
            
                  <input type="text" name="address" id="company-website" v-model="form.address" class="focus:ring-indigo-500 focus:border-indigo-500 flex-1 block w-full rounded-none rounded-r-md sm:text-sm border-gray-300" placeholder="Enter Address" required>
                </div>
              </div>
            </div>

          
          </div>
          <div class="px-4 py-3 bg-gray-50 text-right sm:px-6">
            <button type="submit" class="inline-flex justify-center py-2 px-4 border border-transparent shadow-sm text-sm font-medium rounded-md text-white bg-indigo-600 hover:bg-indigo-700 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-indigo-500" >
              Save
            </button>
          </div>
        </div>
      </form>
    </div>
  </div>
</div>

<div class="hidden sm:block" aria-hidden="true">
  <div class="py-5">
    <div class="border-t border-gray-200"></div>
  </div>
</div>

            <div class="hidden sm:block" aria-hidden="true">
              <div class="py-5">
                <div class="border-t border-gray-200"></div>
              </div>
            </div>
            </div>
        </div>
    </BreezeAuthenticatedLayout>
</template>

<script setup>
import BreezeAuthenticatedLayout from '@/Layouts/Authenticated.vue'
import { Head,Link, useForm } from '@inertiajs/inertia-vue3';



   export default{
     data() {
       return {
         isEditing: false,
       }
     },

     methods:{
       defineProps({
          student:Object,
       });
     }
   }

    const form = useForm({
        name: '',
        address: '',
    });

    function submitForm() {
        form.post('store');
    }


</script>
