<script setup>
    import AuthenticatedLayout from '@/Layouts/AuthenticatedLayout.vue';
    import { Head, Link } from '@inertiajs/vue3';
    import moment from 'moment'
    import { inject } from 'vue';
    const props  = defineProps({
        sales : Array,
        // client: Object
    })

    function formattedDate(date){
        return moment(date).format('MMMM   D, YYYY');
    }
    const themeMode = inject('themeMode');
</script>

<template>
    <Head title="Sales" />

    <AuthenticatedLayout>
        <template #header>
            <h2 class="font-semibold text-xl leading-tight">Sales List</h2>
        </template>

        <div class="py-12">
            <diV style="margin-left:170px;">
                <h1 class="text-3xl font-medium text-gray-700 "></h1>
                <Link href="sales/create"  as="button" class="btn-primary inline-flex items-center mr-20 px-2 py-2 bg-blue-600 border border-transparent rounded-md font-semibold text-xs text-white uppercase tracking-widest hover:bg-blue-700 focus:bg-blue-700 active:bg-blue-900 focus:outline-none focus:ring-2 focus:ring-indigo-500 focus:ring-offset-2 transition ease-in-out duration-150">
                    Create Sales +</Link>
            </div>
            <div class="max-w-7xl mx-auto sm:px-6 lg:px-8 mt-3" :class="themeMode">
                <div class="">
                    <!-- component -->
                    <div class="overflow-hidden rounded-lg border border-gray-200 shadow-md m-5" >
                    <table class="w-full border-collapse  text-left text-sm "  >
                        <thead class=""  >
                        <tr>
                            <th scope="col" class="px-6 py-4 font-medium">Date</th>
                            <th scope="col" class="px-6 py-4 font-medium">Client</th>
                            <th scope="col" class="px-6 py-4 font-medium">Payment</th>
                            <th scope="col" class="px-6 py-4 font-medium">Action</th>
                        </tr>
                        </thead>
                        <tbody class="divide-y divide-gray-100 border-t border-gray-200" v-for="sale in sales" :key="sale.id">
                        <tr>
                            <th class="flex gap-3 px-6 py-4 font-normal">

                            <div class="text-sm">
                                <div class="font-medium ">{{ formattedDate(sale.date ) }}</div>

                            </div>
                            </th>
                            <td class="px-6 py-4">{{ sale.client.first_name }} {{ sale.client.last_name }}</td>
                            <td class="px-6 py-4">  {{ sale.is_credit ? 'Credit' : 'Cash' }}</td>



                            <td class="px-6 py-4">
                            <div class="flex justify-start gap-4">
                                <a x-data="{ tooltip: 'Delete' }" href="#">
                                <button style="color:red;" type="submit">
                                    Delete
                                </button>
                                </a>
                                <a x-data="{ tooltip: 'Edite' }" href="#">
                                <button style="color:green;" type="submit">
                                    Update
                                </button>
                                </a>
                            </div>
                            </td>
                        </tr>

                        </tbody>
                    </table>
                    </div>
                </div>
            </div>
        </div>
    </AuthenticatedLayout>

</template>
