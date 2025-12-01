<template>
  <div class="p-5">
    <button @click="handleClick"
      class="w-10 h-10 bg-slate-600 rounded-full flex items-center justify-center hover:scale-125 border border-white-100 transition-transform duration-300 ease-out">
      <Icon :name="iconName" style="color: white" size="20px"></Icon>
    </button>
  </div>
</template>

<script lang="ts" setup>
import { computed } from 'vue';

const props = defineProps({
  isDark: {
    type: Boolean,
    required: true
  }
})
const emit = defineEmits(['toggle-theme'])
const iconName = computed(() => (
  props.isDark ? 'mdi:moon-waning-crescent' : 'mdi:white-balance-sunny'
))

const handleClick = () => {
  emit('toggle-theme')
}

</script>

<style></style>