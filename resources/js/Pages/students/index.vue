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
                <div class="flex justify-end m-2 p-2">
                <Link href="/students-create" class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded">
                    Add Student
                </Link>
            </div>
                <div class="flex flex-col">
  <div class="-my-2 overflow-x-auto sm:-mx-6 lg:-mx-8">
    <div class="py-2 align-middle inline-block min-w-full sm:px-6 lg:px-8">
      <div class="shadow overflow-hidden border-b border-gray-200 sm:rounded-lg">
        <table class="min-w-full divide-y divide-gray-200">
          <thead class="bg-gray-50">
            <tr>
              <th scope="col" class="px-6 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider">
                Name
              </th>
              <th scope="col" class="px-6 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider">
                Address
              </th>
             
              <th scope="col" class="relative px-6 py-3">
                <span class="sr-only">Edit</span>
              </th>
            </tr>
          </thead>
          <tbody class="bg-white divide-y divide-gray-200">
            <tr v-for="student in students" :key="student.id">
              <td class="px-6 py-4 whitespace-nowrap">
                <div class="flex items-center">
                  <div class="flex-shrink-0 h-10 w-10">
                    <img class="h-10 w-10 rounded-full" src="https://images.unsplash.com/photo-1494790108377-be9c29b29330?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=facearea&facepad=4&w=256&h=256&q=60" alt="">
                  </div>
                  <div class="ml-4">
                    <div class="text-sm font-medium text-gray-900">
                      {{student.name}}
                    </div>

            

                  </div>
                </div>
              </td>



               <td class="px-6 py-4 whitespace-nowrap">
                <div class="flex items-center">
                  <div class="ml-4">
                    <div class="text-sm font-medium text-gray-900">
                     {{student.address}}
                    </div>
                  </div>
                </div>
              </td>
             
            
            
              <td class="px-6 py-4 whitespace-nowrap text-right text-sm font-medium">
                <Link :href="`/students/${student.id}`" class="text-indigo-600 hover:text-indigo-900">Edit</Link>
              </td>
            </tr>
             
            <!-- More people... -->
          </tbody>
        </table>
      </div>
    </div>
  </div>
</div>
            </div>
        </div>
    </BreezeAuthenticatedLayout>
</template>

<script setup>
    import BreezeAuthenticatedLayout from '@/Layouts/Authenticated.vue'
    import { Head,Link } from '@inertiajs/inertia-vue3';
    import PaginationVue from '../Pagination/Pagination.vue';
    

    const props = defineProps({
        students: Array,
    });
</script>
