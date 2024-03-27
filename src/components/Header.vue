<script setup>
defineProps({
    text: String,
});

//constは値の書き換えを禁止した変数を宣言できる．
//大文字と_で変数名を書くと一目でわかる．
const TITLE = "都道府県別の総人口推移"
</script>

<template>
    <div>
        <h1>{{ TITLE }}</h1>
    </div>
</template>