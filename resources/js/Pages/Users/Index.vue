<script setup>
import AppLayout from "@/Layouts/AppLayout.vue";

defineProps({
    users: Object,
});
</script>

<template>
    <AppLayout title="Dashboard">
        <template #header>
            <h2 class="font-semibold text-xl text-gray-800 leading-tight">
                Dashboard
            </h2>
        </template>

        <div class="py-12">
            <div class="max-w-7xl mx-auto sm:px-6 lg:px-8">
                <div class="bg-white overflow-hidden shadow-xl sm:rounded-lg">
                    <table class="w-full text-sm text-left text-gray-500">
                        <thead
                            class="text-xs text-gray-700 uppercase bg-gray-200"
                        >
                            <tr class="text-center">
                                <th class="py-3 px-6">ID</th>
                                <th class="py-3 px-6">Person</th>
                                <th class="py-3 px-6">Phone</th>
                                <th class="py-3 px-6">Email</th>
                            </tr>
                        </thead>
                        <tbody>
                            <template
                                v-for="(user, index) in users"
                                :key="user.id"
                            >
                                <tr
                                    class="bg-white text-center"
                                    :class="{ 'border-t': index }"
                                >
                                    <td class="py-4 px-6">{{ user.id }}</td>
                                    <td class="py-4 px-6">{{ user.name }}</td>
                                    <td class="py-4 px-6">{{ user.phone }}</td>
                                    <td class="py-4 px-6">{{ user.email }}</td>
                                </tr>
                            </template>
                        </tbody>
                    </table>
                </div>
            </div>
        </div>
    </AppLayout>
</template>
