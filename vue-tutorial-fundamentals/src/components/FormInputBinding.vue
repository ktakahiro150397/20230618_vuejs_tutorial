<script setup>

import { ref } from 'vue'

defineProps({
    text:{
        type:String,
        required:true,
    }
})

const inputMessage = ref("")
// inputMessage.value = text

</script>


<template>
    <p>
        FormInputBinding.vue
    </p>
    <div>
        <!-- フォームの入力要素の状態と、対応するJavaScriptの状態を同期する
        これを手動で行うのは面倒(らしい) -->
        <input 
        :value="inputMessage"
        @input="event => inputMessage = event.target.value" placeholder="面倒version" />
    </div>

    <div>
        <input v-model="inputMessage" placeholder="v-model version">
    </div>
</template>