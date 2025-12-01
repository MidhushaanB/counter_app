<template>
    <div :class="['min-h-screen transition-colors duration-300', isDark ? 'bg-background_primary' : 'bg-white']">
        <Header :isDark="isDark" @toggle-theme="toggleTheme" />
        <div class="flex justify-center align-middle">
            <div class="flex flex-col justify-center align-middle">
                <InptBox :isDark="isDark" :count="count" />
                <div class="flex flex-row justify-evenly align-middle mt-10">
                    <PlusNMinusBtn @increment="increment" @decrement="decrement" :isDark="isDark" />
                    <ResetBtn @reset="reset"/>
                </div>
            </div>
        </div>
    </div>
</template>

<script lang="ts" setup>
import { ref, onMounted, watch } from 'vue';
import PlusNMinusBtn from '~/components/PlusNMinusBtn.vue';
import ResetBtn from '~/components/ResetBtn.vue';

const isDark = ref(false)
const count = ref(0)

watch(isDark, (newVal) => {
    const themeString = newVal ? 'dark' : 'light';
    localStorage.setItem('theme', themeString);
})
onMounted(() => {
    const savedTheme = localStorage.getItem('theme');

    if (savedTheme === 'dark') {
        isDark.value = true;
    } else if (savedTheme === 'light') {
        isDark.value = false;
    }
})

const increment = () => {
    count.value++
}
const decrement = () => {
    count.value--
}
const reset = () => {
    count.value = 0
}

const toggleTheme = () => {
    isDark.value = !isDark.value;
}
</script>

<style></style>