<template>
    <div class="flex">
        <div class="w-full" :class="{ 'xl:pr-60': productsAmount > 0 && $route.name !== 'cart' }">
            <Navbar />

            <div class="container mx-auto p-8">
                <slot />
            </div>
        </div>

        <Sidebar />
    </div>
</template>

<script setup>
import { productsStore } from '../store/productsStore'
import { storeToRefs } from 'pinia';

const store = productsStore()

const { productsAmount } = storeToRefs(store)
</script>
