<template>
    <div class="toggle-wrapper">
        <label class="toggle">
            <input type="checkbox" :checked="(mode === 'dark') ? 'checked' : false" @change="toggle">
            <span class="toggler"></span>
        </label>
    </div>
</template>

<script setup>

const props = defineProps(['mode'])

const emit = defineEmits(['toggle'])

const toggle = () => {
    emit('toggle')
}

</script>

<style scoped lang="scss">
.toggle {
    position: relative;
    display: inline-block;
    width: 60px;
    height: 34px;

    input {
        opacity: 0;
        width: 0;
        height: 0;

        &:checked+.toggler {
            background-color: #2196f3;
        }

        &:checked+.toggler:before {
            transform: translateX(26px);
        }
    }

    .toggler {
        position: absolute;
        cursor: pointer;
        top: 0;
        left: 0;
        right: 0;
        bottom: 0;
        background-color: #15205b;
        transition: 0.4s;
        border-radius: 20px;

        &:before {
            position: absolute;
            content: "";
            height: 26px;
            width: 26px;
            left: 4px;
            bottom: 4px;
            background-color: #fff;
            border-radius: 50%;
            transition: 0.4s;
        }
    }
}
</style>