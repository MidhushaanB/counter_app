<template>
  <button @click="emit('reset')"
    class="h-14 w-14 flex justify-center align-middle items-center rounded-full bg-blue-700 transform transition-transform duration-300 hover:scale-125">
    <Icon name="mdi:restart" size="24px" class="text-white" />
  </button>
</template>

<script lang="ts" setup>
    const emit = defineEmits(['reset'])
</script>

<style>

</style>