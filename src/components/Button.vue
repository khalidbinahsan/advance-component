<script setup>
const props = defineProps({
    label: {
        type: Number,
        default: 'Button'
    },
    color: {
        type: String,
        default: "blue"
    }
})

function btnBG() {
    return `bg-${props.color}-500 hover:bg-${props.color}-700`;
}
</script>

<template>
<button class="py-2 px-4 rounded text-white uppercase" :class="btnBG()">{{ label }}</button>
</template>

<style scoped>

</style>