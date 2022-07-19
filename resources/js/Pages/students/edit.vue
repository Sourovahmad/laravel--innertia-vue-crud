<template>
  {{ student.name }}
</template>

<script setup>
       
        const props = defineProps({
            student:Object,
        });
</script>

