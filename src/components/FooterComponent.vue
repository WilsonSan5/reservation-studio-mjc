<script setup>

function redirectTo(url) {
    window.location.href = url;
}
</script>

<template>
    <footer>
        <!--Wave shape -->
        <div class="custom-shape-divider-top">
            <svg data-name="Layer 1" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1200 120"
                preserveAspectRatio="none">
                <path
                    d="M321.39,56.44c58-10.79,114.16-30.13,172-41.86,82.39-16.72,168.19-17.73,250.45-.39C823.78,31,906.67,72,985.66,92.83c70.05,18.48,146.53,26.09,214.34,3V0H0V27.35A600.21,600.21,0,0,0,321.39,56.44Z"
                    class="shape-fill"></path>
            </svg>
        </div>
        <!-- End Wave shape -->
        <div class="logo-wrapper">
            <img src="/bdc_logo.jpg" alt="logo de la boite de concert"
                @click="redirectTo('https://mjcpontault.fr/bdc')" />
            <img src="/mjc_logo.png" alt="logo de la MJC Boris Vian" @click="redirectTo('https://mjcpontault.fr/')" />
        </div>
        <div>
            <p>Copyright © 2024 MJC Pontault-Combault. Développé par Wilson San</p>
        </div>
    </footer>
</template>

<style scoped>
footer {
    display: flex;
    flex-direction: column;
    align-content: space-between;

    padding: 1rem;
    margin: 0;
    position: relative;
    height: auto;
}

#slide-up-btn {
    margin: auto;
    margin-bottom: 20px;
    margin-top: 35px;
    width: 70px;
    cursor: pointer;
}

footer .logo-wrapper {
    text-align: center;
    margin-top: 50px;
    margin-bottom: auto;
}

footer .logo-wrapper img {
    border-radius: 20px;
    margin: 0 10px;
}

footer p {
    margin: 0;
    margin-top: 10px;

    color: white;
    font-weight: 400;
    text-align: center;
}

footer::after {
    content: "";
    position: absolute;
    left: -2rem;
    top: 0;
    z-index: -1;
    display: flex;
    height: 100%;
    width: 110vw;
    background-color: var(--brown-color);
}

/* Wave shape */

.custom-shape-divider-top {
    position: absolute;
    top: 0px;
    left: 0;

    width: 100%;
    overflow: hidden;
    line-height: 0;

    transform: scaleX(150%);
}

.custom-shape-divider-top svg {
    position: relative;
    display: block;
    width: calc(100% + 1.3px);
    height: 50px;
}

.custom-shape-divider-top .shape-fill {
    fill: var(--pink-color);
}
</style>
