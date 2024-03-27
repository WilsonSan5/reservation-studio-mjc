<script setup>
</script>

<template>
    <div id="component-wrapper" class="container">
        <p>Tu as une question ?</p>
        <button id="open-form-btn"> contacte nous</button>
    </div>
</template>

<style scoped>
#component-wrapper {
    margin-top: 2em;
    /* border: 1px solid blue; */
    display: flex;
    flex-direction: column;
}

#component-wrapper p {
    font-size: 1.5em;
    text-align: center;
}

#component-wrapper button {
    margin: 1em auto;
    width: 200px;
    padding: 15px 0;
    border-radius: 10px;
    border: none;
    background-color: rgb(24, 24, 24);

    font-size: 1.2em;
}
</style>