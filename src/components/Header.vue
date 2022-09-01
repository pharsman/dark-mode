<template>
    <header>
        <h1>{{ mode }} Mode</h1>
        <Toggle @toggle="toggle" />
        <nav>
            <div class="nav-link">Home</div>
            <div class="nav-link">About</div>
            <div class="nav-link">Portfolio</div>
            <div class="nav-link">Contact</div>
        </nav>
    </header>
</template>

<script setup>
import Toggle from './Toggle.vue';

const emit = defineEmits(['toggle'])

const toggle = () => {
    emit('toggle')
}

const props = defineProps({
    mode: {
        type: String,
        required: true
    }
})

</script>

<style scoped lang="scss">
header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 0px 25px;
    height: 60px;
    background-color: #C3C3C3;
    transition: background-color 0.3s ease-in-out;

    h1 {
        font-size: 32px;
        text-transform: uppercase;
        font-weight: bold;
    }

    nav {
        display: flex;
        height: 60px;

        .nav-link {
            display: flex;
            align-items: center;
            padding: 0 15px;
            cursor: pointer;

            &:hover {
                background-color: #B0B0B0;
            }
        }
    }
}

.dark header {
    background-color: #15202b;

    nav {
        .nav-link {
            &:hover {
                background-color: #202020;
            }
        }
    }
}
</style>