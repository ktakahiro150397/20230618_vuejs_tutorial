

<script setup>
import { ref } from 'vue'

// ref()でリアクティブ状態を宣言する
// ref()は「深いリアクティブ」になる 
// => 配列の値を変更した場合でも再レンダリングがトリガーする
const count = ref(0)

function increment(){
    count.value++
}

defineProps({
        msg:{
            type:String,
            required:true
        },
        color:{
            type:String,
            required:false,
        },
        disabled:{
            type:Boolean,
            required:false,
        }
    })
</script>

<script>
function InTemplateFunction(){
    return "This is string returned from function in template."
}

function onClickToggle(){
    console.log("clicked!");
    disabled = !disabled;
}
</script>

<template>
    <div>
        <!-- イベントの処理を@...で記載 -->
        <input type="button" @click="increment" value="increment value" />
        <p>
            <!-- テンプレート中ではref()が自動でアンラップされる -->
            count : {{ count }}
        </p>

        <p>
            <!-- マスタッシュ構文 / テキストの展開 -->
            Message : {{ msg }}
        </p>
        <!-- ディレクティブ / Vueから提供されている特別な属性 -->
        <!-- コンパイル時に特定の振る舞いを与える -->
        <p>Message(v-html) : <span v-html="msg"></span></p>

        <!-- 属性バインディング / 属性にはマスタッシュ構文が使用できない。v-bind:xxxを使用する -->
        <!-- v-bind:xxxは特に、:xxx と記載することもできる -->
        <!-- 三項演算子でスタイルを分岐している。割りとやりたい放題できる？ -->
        <!-- →テンプレート内部ではJavaScript式を自由に記載できる -->
        <p>
            <span :style="color ? `color:${color}` : ''">Message(v-bind:style) : {{ msg }}</span>
        </p>

        <p>
            <!-- 関数呼び出しもできるが、更新のたびに呼び出される。副作用をもたせないようにする！ -->
            InTemplateFunction! : {{ InTemplateFunction() }}
        </p>

        <input type="button" value="toggle" v-on:click="onClickToggle" />
        <input type="text" :disabled="disabled" />
        
    </div>
</template>