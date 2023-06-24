<script setup>
import { ref } from "vue";

const items = ref([
  { message: "message1" },
  { message: "message2" },
  { message: "message3" },
  { message: "message4" },
  { message: "message5" },
]);

const propEnum = ref({
    prop1: "test_prop1",
    prop2: "test_prop2",
    prop3: "test_prop3",
    prop4: "test_prop4",
    prop5: "test_prop5",
})

function onClickPropPush(){
    items.value.push({message:"AddItem!"})
}
</script>

<template>
  <!-- v-forによるコレクションの反復 -->
  <button @click="onClickPropPush">Add Item</button>
  <li v-for="item in items">
    {{ item.message }}
  </li>

  <div>
    <p>インデックス付きの列挙</p>
    <!-- インデックスも参照OK -->
    <li v-for="(item, index) in items">
      {{ index + " " + item.message }}
    </li>
  </div>

  <div>
    <p>プロパティの列挙</p>
    <li v-for="(value,key,index) in propEnum">
        {{ key + " " + value + " " + index }}
    </li>
  </div>

  <div>
    <p>整数値の列挙</p>
    <span v-for="n in 10">{{ n }}</span>
  </div>
</template>
