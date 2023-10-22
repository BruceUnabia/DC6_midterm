<script setup>
    import AuthenticatedLayout from '@/Layouts/AuthenticatedLayout.vue';
    import { Head } from '@inertiajs/vue3';

    const props  = defineProps({
        products : Object
    })
</script>

<template>
    <Head title="Update Product" />

    <AuthenticatedLayout>
        <template>
        </template>

        <div class="min-h-screen bg-gray-100 flex justify-center items-center">
    <div class="bg-white shadow-lg rounded-3xl sm:max-w-xl sm:mx-auto p-6 sm:p-10 mx-8 md:mx-0">
        <div class="max-w-md mx-auto">
            <h2 class=" text-center text-2xl font-semibold text-gray-700 mb-4">Edit Product</h2>
            <hr class="border-t-2 border-gray-200 mb-4">
            <div class="divide-y divide-gray-200 space-y-4">
                <div class="flex flex-col">
                    <label for="brand" class="text-sm mb-1">Brand</label>
                    <input type="text" id="brand" class="py-2 px-4 rounded border w-full focus:outline-none focus:border-gray-900" placeholder="">
                </div>
                <div class="flex flex-col">
                    <label for="name" class="text-sm mb-1">Name</label>
                    <input type="text" id="name" class="py-2 px-4 rounded border w-full focus:outline-none focus:border-gray-900" placeholder="">
                </div>
                <div class="flex space-x-4">
                    <div class="flex flex-col w-1/2">
                        <label for="retailPrice" class="text-sm mb-1">Retail Price</label>
                        <input type="number" id="retailPrice" class="py-2 px-4 rounded border w-full focus:outline-none focus:border-gray-900" placeholder="">
                    </div>
                    <div class="flex flex-col w-1/2">
                        <label for="qtyStock" class="text-sm mb-1">Qty Stock</label>
                        <input type="number" id="qtyStock" class="py-2 px-4 rounded border w-full focus:outline-none focus:border-gray-900" placeholder="">
                    </div>
                </div>
                <div class="flex flex-col">
                    <label for="category" class="text-sm mb-1">Category</label>
                    <select id="category" class="py-2 px-4 rounded border w-full focus:outline-none focus:border-gray-900">
                        <option value="" disabled>Select Category</option>
                        <option>Smartphones</option>
                    </select>
                </div>
                <div class="pt-4 flex space-x-4">
                    <button class="bg-blue-600 flex items-center justify-center w-full py-3 rounded-md text-white focus:outline-none">Update</button>
                    <button class="bg-gray-600 flex items-center justify-center w-full py-3 rounded-md text-gray-900 focus:outline-none">
                         Cancel
                    </button>

                </div>
            </div>
        </div>
    </div>
</div>


    </AuthenticatedLayout>

</template>
