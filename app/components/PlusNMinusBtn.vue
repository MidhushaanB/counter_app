<template>
    <div class="flex gap-7">

        <button type="button" @click="emit('increment')"
            class="h-14 w-14 rounded-full bg-slate-800 flex justify-center align-middle items-center  hover:scale-125 transform transition-transform duration-300 ease-out">
            <Icon name="mdi:plus" size="24" class="text-white" />
        </button>

        <button type="button" @click="emit('decrement')"
            class="h-14 w-14 rounded-full bg-slate-800 flex justify-center align-middle items-center hover:scale-125 transform transition-transform duration-300 ease-out">
            <Icon name="mdi:minus" size="24" class="text-white" />
        </button>
    </div>
</template>

<script lang="ts" setup>
import { NuxtIconCss } from '@nuxt/icon/runtime/components/css.js';
const emit = defineEmits(['increment', 'decrement'])
const props = defineProps(['isDark'])
console.log(props.isDark);
</script>

<style></style>