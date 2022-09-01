<template>
    <div class="light" :class="(mode === 'dark') ? 'dark' : 'light'">
        <Header :mode="mode" @toggle="toggle" />
        <Content :mode="mode" />
    </div>
</template>

<script setup>
import Header from '@/components/Header.vue'
import { ref } from 'vue';
import Content from '@/components/Content.vue';

const mode = ref('dark')

const toggle = () => {
    if (mode.value === 'dark') {
        mode.value = 'light'
    } else if (mode.value === 'light') {
        mode.value = 'dark'
    }
}

function keyPress(e) {
    if (e.key === 't') {
        toggle()
    }
}

window.addEventListener('keyup', keyPress)

</script>

<style  lang="scss">
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    font-family: 'Roboto', sans-serif;
}

.light {
    width: 100vw;
    min-height: 100vh;
    background-color: #f3f3f3;
    color: #15202b;
}

.dark {
    background-color: #192734;
    color: #e8e8e8;
}
</style>