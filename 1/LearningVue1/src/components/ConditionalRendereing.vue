<script setup>
import { ref } from 'vue';

let isVisible = ref(true);

function toggleVisibility() {
    isVisible.value = !isVisible.value;
}
</script>

<template>
    <p v-show="isVisible">This paragraph will only show or hide when toggled.</p>
    <button @click="toggleVisibility">Toggle Visibility</button>
</template>
