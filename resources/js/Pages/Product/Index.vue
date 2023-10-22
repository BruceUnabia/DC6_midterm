<script setup>
    import AuthenticatedLayout from '@/Layouts/AuthenticatedLayout.vue';
    import { Head, Link, router, useForm } from '@inertiajs/vue3';
    import { inject } from 'vue';

    const props  = defineProps({
        products : Object
    })

    let deleteForm = useForm({});
    let selectedProductForDelete = null

    function remove(prod) {
        selectedProductForDelete = prod
        deleteForm.delete('/products/' + selectedProductForDelete.id)

        // console.log(props.errors)
    }


    const themeMode = inject('themeMode');

</script>

<template>
    <Head title="Product" />

    <AuthenticatedLayout>
        <template #header>
            <h2 class="font-semibold text-xl leading-tight">Product List</h2>
        </template>

        <div class="py-2">
            <div style="margin-left: 170px">
                <h1 class="text-3xl font-medium text-gray-700"></h1>
                <Link href="products/create" as="button" class="items-center mr-20 px-2 py-2 bg-blue-600 border border-transparent rounded-md font-semibold text-xs text-white uppercase tracking-widest focus:bg-blue-700 active:bg-blue-900 focus:outline-none focus:ring-2 focus:ring-indigo-500 focus:ring-offset-2 transition ease-in-out duration-150">
                    Create Product +
                </Link>
            </div>
            <div class="max-w-7xl mx-auto sm:px-6 lg:px-8">
                <div class="" :class="themeMode">
                    <div class="m-5" v-for="prod in products" :key="prod.id">
                        <div class="overflow-hidden rounded-lg border border-gray-200 shadow-md mb-5">
                            <div class="px-6 py-4">
                                <h3 class="text-xl font-semibold">{{ prod.name }}</h3>
                                <p class="text-gray-700">{{ prod.description }}</p>
                            </div>
                            <div class="px-6 py-4">
                                <div class="flex items-center">
                                    <p class="text-sm font-medium text-gray-700">Retail Price:</p>
                                    <p class="ml-2 text-sm text-gray-600">{{ prod.retail_price }}</p>
                                </div>
                                <div class="flex items-center">
                                    <p class="text-sm font-medium text-gray-700">Stock Qty:</p>
                                    <p class="ml-2 text-sm text-gray-600">{{ prod.qty_stock }}</p>
                                </div>
                                <div class="flex items-center">
                                    <p class="text-sm font-medium text-gray-700">Category:</p>
                                    <p class="ml-2 text-sm text-gray-600">{{ prod.category.name }}</p>
                                </div>
                            </div>
                            <div class="px-6 py-4">
                                <div class="flex justify-start gap-4">
                                    <button style="color:red;" @click="remove(prod)" x-data="{ tooltip: 'Delete' }" href="#">
                                        Delete
                                    </button>
                                    <Link style="color:green;" x-data="{ tooltip: 'Edit' }" :href="'/products/edit/' + prod.id">
                                        Update
                                    </Link>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </AuthenticatedLayout>
</template>
