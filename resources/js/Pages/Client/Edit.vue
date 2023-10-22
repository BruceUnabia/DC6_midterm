<script setup>
    import AuthenticatedLayout from '@/Layouts/AuthenticatedLayout.vue';
    import { Head } from '@inertiajs/vue3';

    const props  = defineProps({
        clients : Object
    })
</script>

<template>
    <Head title="Update Client" />

    <AuthenticatedLayout>
        <template>
        </template>

        <div class="min-h-screen flex items-center justify-center">
    <div class="bg-white rounded-lg shadow-lg p-6 w-80">
        <h1 class="text-2xl font-semibold text-center mb-4">Edit Client Information</h1>
        <hr class="border-t-2 border-gray-200 mb-4">

        <form class="space-y-4">
            <div class="flex flex-col">
                <label for="firstname" class="text-sm mb-1">First Name</label>
                <input type="text" id="firstname" class="py-2 px-4 rounded border w-full focus:outline-none focus:border-blue-400" placeholder="First Name">
            </div>

            <div class="flex flex-col">
                <label for="lastname" class="text-sm mb-1">Last Name</label>
                <input type="text" id="lastname" class="py-2 px-4 rounded border w-full focus:outline-none focus:border-blue-400" placeholder="Last Name">
            </div>

            <div class="flex flex-col">
                <label for="address" class="text-sm mb-1">Address</label>
                <input type="text" id="address" class="py-2 px-4 rounded border w-full focus:outline-none focus:border-blue-400" placeholder="Address">
            </div>

            <div class="flex flex-col">
                <label for="phone" class="text-sm mb-1">Phone Number</label>
                <input type="tel" id="phone" class="py-2 px-4 rounded border w-full focus:outline-none focus:border-blue-400" placeholder="Phone Number">
            </div>

            <div class="flex flex-col">
                <label for="credit" class="text-sm mb-1">Credit Limit</label>
                <input type="number" id="credit" class="py-2 px-4 rounded border w-full focus:outline-none focus:border-blue-400" placeholder="Credit Limit">
            </div>

            <div class="flex justify-center space-x-4">
                <button type="submit" class="py-3 w-1/2 text-white bg-blue-600 rounded-lg hover:bg-blue-700">Update</button>
                <button type="button" class="py-3 w-1/2 text-white bg-gray-600 rounded-lg hover:bg-gray-700">Cancel</button>
            </div>
        </form>
    </div>
</div>
    </AuthenticatedLayout>

</template>
