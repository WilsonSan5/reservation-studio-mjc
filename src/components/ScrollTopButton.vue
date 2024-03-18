<script setup>
import { ref, onMounted } from 'vue'
function scrollToTop() {
    window.scrollTo({ top: 0, behavior: "smooth" });
}
const isScrollingUp = ref()
const windowTop = ref()
let previousScrollPosition = 0;

function onScroll() {
    // remove button when Calendly widget is on sight
    if (window.top.scrollY < 250) {
        isScrollingUp.value = false
        return
    }

    if (window.top.scrollY > windowTop.value) {
        isScrollingUp.value = false
    } else {
        isScrollingUp.value = true
    }
    windowTop.value = window.top.scrollY
}
onMounted(() => {
    window.addEventListener('scroll', onScroll)
})

</script>

<template>
    <img src="/icons/up-arrow.svg" alt="bouton pour remonter en haut de la page" id="slide-up-btn"
        :class="{ show: isScrollingUp }" @click="scrollToTop" />
</template>

<style scoped>
#slide-up-btn {
    width: 70px;
    position: fixed;
    z-index: 2;
    bottom: 20px;
    right: -100px;

    filter: drop-shadow(3px 3px 1px rgb(0 0 0 / 0.4));
    transition: 0.2s ease-in-out;
}

.show {
    position: fixed;
    right: 15px !important;
}

/* Safari 7.1+ */

_::-webkit-full-page-media,
_:future,
:root #slide-up-btn {
    bottom: 60px;
}
</style>