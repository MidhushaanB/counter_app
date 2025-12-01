<template>
    <div class="">
        <input 
        type="text" 
        class="bg-slate-700 border rounded-xl w-full px-5 py-10 shadow-xs"
        :value="count"
        readonly/>
    </div>
</template>

<script lang="ts" setup>
    const props = defineProps(['count'])
</script>

<style>

</style>