<template>
    <div class="flex gap-3">

        <button type="button" @click="emit('increment')"
            class="h-14 w-14 rounded-full bg-slate-800 flex justify-center align-middle items-center">
            <Icon name="mdi:plus" size="24" class="text-white"/>
        </button>

        <button type="button" @click="emit('decrement')"
            class="h-14 w-14 rounded-full bg-slate-800 flex justify-center align-middle items-center">
            <Icon name="mdi:minus" size="24" class="text-white" />
        </button>
    </div>
</template>

<script lang="ts" setup>
import { NuxtIconCss } from '@nuxt/icon/runtime/components/css.js';
const emit = defineEmits(['increment', 'decrement'])

</script>

<style></style>