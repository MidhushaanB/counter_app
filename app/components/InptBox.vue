<template>
    <div class="flex items-center justify-center">
        <!-- Glow background, similar to the React version -->
        <div class="relative">
            <div class="absolute inset-0 bg-blue-500/10 rounded-3xl blur-2xl"
                :class="isDark ? 'dark-glow' : 'light-glow'" />

            <!-- Main card -->
            <div :class="[
                'relative rounded-3xl shadow-xl px-16 py-12 min-w-[280px] flex items-center justify-center border transition-colors duration-300',
                isDark ? 'bg-slate-800 border-slate-700' : 'bg-white border-slate-200'
            ]">
                <!-- Animated number -->
                <Transition name="slide-fade" mode="out-in">
                    <p :key="count" :class="[
                        'text-7xl font-bold tabular-nums',
                        isDark ? 'text-white' : 'text-slate-900'
                    ]">
                        {{ count }}
                    </p>
                </Transition>
            </div>
        </div>
    </div>
</template>

<script lang="ts" setup>
const props = defineProps(['isDark', 'count'])
</script>

<style scoped>
.slide-fade-enter-active,
.slide-fade-leave-active {
    transition: all 0.2s ease-out;
}

.slide-fade-enter-from {
    opacity: 0;
    transform: translateY(20px);
}

.slide-fade-leave-to {
    opacity: 0;
    transform: translateY(-20px);
}

</style>