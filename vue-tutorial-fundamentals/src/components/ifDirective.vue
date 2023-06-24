<script setup>

import { ref } from 'vue'

const isDisplay = ref(false)

</script>


<template>
    <button @click="isDisplay = !isDisplay">Toggle Display</button>

    <!-- v-ifディレクティブ / v-ifの直後にないと認識されない -->
    <!-- v-ifはDOMにそもそも現れない -->
    <p v-if="isDisplay">isDisplay = true!</p>
    <p v-else>isDisplay = false!</p>

    <!-- v-showディレクティブ / v-showはDOMには現れるが、display:noneになる -->
    <!-- v-elseに当たるものはない -->
    <p v-show="isDisplay">v-show isDisplay= true!</p>
    <p v-show="!isDisplay">v-show isDisplay= false!</p>

    <!-- DOM操作を行うため、v-ifの方が実行コストが高い -->
</template>