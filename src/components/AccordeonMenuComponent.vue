<script setup>
import AccordeonItemComponent from "./AccordeonItemComponent.vue";
</script>

<template>
    <section class="section-wrapper">
        <div class="custom-shape-divider-top">
            <svg data-name="Layer 1" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1200 120"
                preserveAspectRatio="none">
                <path
                    d="M321.39,56.44c58-10.79,114.16-30.13,172-41.86,82.39-16.72,168.19-17.73,250.45-.39C823.78,31,906.67,72,985.66,92.83c70.05,18.48,146.53,26.09,214.34,3V0H0V27.35A600.21,600.21,0,0,0,321.39,56.44Z"
                    class="shape-fill"></path>
            </svg>
        </div>
        <div class="container accordion-menu">
            <!-- Règles -->
            <AccordeonItemComponent title="Règles" maxHeight="1000px">
                <template v-slot:icon>
                    <img src=" /icons/tabler_pin-filled.svg" />
                </template>
                <p><b> Avant :</b></p>
                <ul>
                    <li>
                        Je prépare mon matériel et m’assure du matériel sur place dont j’ai besoin
                    </li>
                    <li>
                        Je signale mon arrivée au bureau le jour J auprès d’un membre de l’équipe, qui
                        m’ouvrira le studio
                    </li>
                </ul>
                <p><b> Pendant :</b></p>
                <ul>
                    <li>
                        Par respect pour les autres activités, je ferme les deux portes du studio
                    </li>
                    <li>Je signale au bureau tout type de problème</li>
                    <li>Je ne mange ni bois dans le studio</li>
                    <li>Je respecte les horaires définit</li>
                </ul>
                <p><b>Après :</b></p>
                <ul>
                    <li>Je remets en place le studio comme je l’ai trouvé à l’arrivée</li>
                    <li>Je ferme les fenêtres, j’éteins les amplis/console et la lumière</li>
                    <li>Je quitte les lieux à l’horaire défini en ayant anticipé le rangement</li>
                    <li>Je signale s’il y a du matériel défectueux</li>
                    <li>Je signale mon départ au bureau</li>
                </ul>
            </AccordeonItemComponent>

            <!-- Instruments et matériel -->
            <AccordeonItemComponent title="Équipement" maxHeight="700px">
                <template v-slot:icon>
                    <img src="/icons/instrument.svg" />
                </template>
                <p><b>Instrument :</b></p>
                <ul>
                    <li>Une batterie (grosse caisse, caisse claire, charleyston)</li>
                    <li>Une guitare électrique</li>
                    <li>Une guitare folk</li>
                    <li>Une guitare classique</li>
                    <li>Une basse</li>
                    <li>Un ukulele</li>
                    <li>Un piano</li>
                </ul>
                <p><b>Matériel :</b></p>
                <ul>
                    <li>Un tableau effaçable</li>
                    <li>Des rallonges jack</li>
                    <li>Des pupitres</li>
                    <li>Des amplis de guitare</li>
                    <li>Un ampli de basse</li>
                </ul>
                <p>
                    Tu peux ramener tes propres instruments. Attention à ne pas les oublier en
                    partant !
                </p>
            </AccordeonItemComponent>

            <!--  Paiement  -->
            <AccordeonItemComponent title="Paiement" maxHeight="200px">
                <template v-slot:icon>
                    <img src="/icons/credit-card.svg" />
                </template>
                <p><b> Tarifs :</b></p>
                <ul>
                    <li>5€ pour 1h</li>
                </ul>
                <p>Le paiement se fera sur place.</p>
            </AccordeonItemComponent>

            <hr />
            <!-- Modele -->
            <!-- <AccordeonItemComponent title="titre...">
                <template v-slot:icon>
                    <img src="source de l'image ...">
                </template>
                <p> Contenu du texte ... </p>
            </AccordeonItemComponent> -->
        </div>
    </section>
</template>

<style scoped>
.section-wrapper {
    margin-top: 1rem;
    padding: 2rem 0;
    position: relative;
    padding-bottom: 50px;
}

.section-wrapper hr {
    height: 2px;
    background-color: black;
    border: 0;
}

.section-wrapper::after {
    position: absolute;
    top: 0;
    left: -2rem;
    z-index: -1;
    content: "";
    display: flex;
    width: 110vw;
    height: 100%;
    background-color: var(--pink-color);
}

.accordion-menu {
    padding-top: 50px;
}

/* Wave shape */

.custom-shape-divider-top {
    position: absolute;
    top: 0px;
    left: 0;
    width: 100%;
    overflow: hidden;
    line-height: 0;
}

.custom-shape-divider-top svg {
    position: relative;
    display: block;
    width: calc(100% + 1.3px);
    height: 30px;
}

.custom-shape-divider-top .shape-fill {
    fill: var(--beige-color);
}
</style>
