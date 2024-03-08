<script setup>
import { onMounted, ref } from "vue";

let isLoaded = ref(false)

setTimeout(() => {
    // Faire apparaitre le widget après 1500ms pour éviter le white screen
    let calendlyWidget = document.getElementById('calendly-inline-widget')
    calendlyWidget.style.opacity = '1'
    isLoaded.value = false
}, 1500)

onMounted(() => {
    let calendlyScript = document.createElement("script");
    calendlyScript.setAttribute(
        "src",
        "https://assets.calendly.com/assets/external/widget.js"
    );
    calendlyScript.setAttribute("async", "true");
    document.head.appendChild(calendlyScript);
});
</script>

<template>
    <div class="loader-wrapper">
        <span v-if="isLoaded == false" class="loader"></span>
    </div>

    <!-- Calendly inline widget begin -->
    <div id="calendly-inline-widget" class="calendly-inline-widget"
        data-url="https://calendly.com/studio-musique-mjcpc/lien-de-reservation?hide_event_type_details=1&hide_gdpr_banner=1&background_color=f3e2d2&primary_color=c64a1b"
        style="width: 320px; height: 600px">
    </div>
    <!-- Calendly inline widget end -->
</template>

<style scoped>
.calendly-inline-widget {
    margin: auto !important;
    margin-top: 1rem;
    overflow-y: hidden !important;
    opacity: 0;

    transition: 0.2s ease-in-out;
}

/* Mobile */
/* Medium */
@media (min-width: 375px) {
    .calendly-inline-widget {
        width: 330px !important;
    }
}

/* Large */
@media (min-width: 425px) {
    .calendly-inline-widget {
        width: 400px !important;
    }
}

/* Desktop */
@media (min-width: 1024px) {
    .calendly-inline-widget {
        width: 600px !important;
    }
}

/*  Loader css */
.loader-wrapper {
    position: absolute;
    top: 350px;
    left: 50%;

    margin-left: -35px;
}

.loader {
    width: 100px;
    height: 100px;
    border-radius: 50%;
    position: relative;

    animation: rotate 1s linear infinite
}

.loader::before {
    content: "";
    width: 70px;
    height: 70px;
    box-sizing: border-box;
    position: absolute;
    inset: 0px;
    border-radius: 50%;
    border: 5px solid var(--brown-color);
    animation: prixClipFix 2s linear infinite;
}

@keyframes rotate {
    100% {
        transform: rotate(360deg)
    }
}

@keyframes prixClipFix {
    0% {
        clip-path: polygon(50% 50%, 0 0, 0 0, 0 0, 0 0, 0 0)
    }

    25% {
        clip-path: polygon(50% 50%, 0 0, 100% 0, 100% 0, 100% 0, 100% 0)
    }

    50% {
        clip-path: polygon(50% 50%, 0 0, 100% 0, 100% 100%, 100% 100%, 100% 100%)
    }

    75% {
        clip-path: polygon(50% 50%, 0 0, 100% 0, 100% 100%, 0 100%, 0 100%)
    }

    100% {
        clip-path: polygon(50% 50%, 0 0, 100% 0, 100% 100%, 0 100%, 0 0)
    }
}
</style>
