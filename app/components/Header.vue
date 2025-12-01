<template>
    <nav class="relative pt-5 flex justify-end">
        <DarkThemeBtn :isDark="isDark" @toggle-theme="handelToggleTheme"/>
    </nav>
</template>

<script lang="ts" setup>

const props = defineProps({
    isDark: {
        type: Boolean,
        required: true
    }
})

const emit = defineEmits(['toggle-theme'])

const handelToggleTheme = () => {
    emit('toggle-theme')
}


</script>

<style></style>