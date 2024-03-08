<script setup>
import { ref } from 'vue';
let isOpen = ref(false)

function toggleAccordion() {
    isOpen.value = !isOpen.value
    const itemWrapper = document.getElementById(props.title)
    if (isOpen.value) {
        itemWrapper.style.maxHeight = props.maxHeight
    } else {
        itemWrapper.style.maxHeight = '10px'
    }
}

var props = defineProps({
    title: String,
    maxHeight: String
})
</script>
<template>
    <div class="item-wrapper" :id="title">
        <div class="item" @click="toggleAccordion">
            <slot name="icon" class="icon"></slot>
            <p class="title">{{ title }}</p>
            <img class="arrow-icon" src="/icons/Vector.svg" :class="{ inverted: isOpen }">
        </div>
        <div class="description">
            <slot></slot>
        </div>
    </div>
</template>

<style>
.item-wrapper {
    padding: 20px 0;
    margin-bottom: 15px;
    border-top: 2px solid black;
    overflow: hidden;
    transition: 0.2s ease-in-out;
    max-height: 10px;
}

.item {
    display: flex;
    align-items: center;
    cursor: pointer;
}

.item img {
    transition: 0.2s ease-in-out;
}

.title {
    margin-right: auto;
    margin-left: 10px;
    font-weight: 600;
    font-size: 1.5em;
}

.description p {
    font-size: 1.2rem;
    margin-top: 30px;
    font-weight: 500;
}

.description b {
    font-size: 1.2rem;
    margin-top: 30px;
    font-weight: 600;
}

ul li {
    text-align: left;
    font-size: 1.1rem;
}

.inverted {
    transition: 0.2s ease-in-out;
    -webkit-transform: rotate(180deg);
}
</style>