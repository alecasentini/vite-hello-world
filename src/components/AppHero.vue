<script>
export default {
    name: "AppHero",
    data() {
        return {
            message: "Clicca sulla carta!",
            isFlipped: false
        }

    },
    methods: {
        flipCard() {
            this.isFlipped = !this.isFlipped;
        }
    }
}
</script>

<template>
    <h2>{{ message }}</h2>
    <div class="flip-card" @click="flipCard">
        <div class="flip-card-inner" :class="{ gira: isFlipped }">
            <div class="flip-card-front">
                <img src="../assets/back-card.jpg" alt="Back">
            </div>
            <div class="flip-card-back">
                <img src="../assets/04.jpg" alt="Charizard">
            </div>
        </div>
    </div>
</template>

<style scoped>
.flip-card {
    background-color: transparent;
    width: 6.3cm;
    height: 8.8cm;
}

.flip-card-inner {
    position: relative;
    width: 100%;
    height: 100%;
    transition: transform 0.8s;
    transform-style: preserve-3d;
}

.gira {
    transform: rotateY(180deg);
}

.flip-card-front,
.flip-card-back {
    position: absolute;
    width: 100%;
    height: 100%;
    -webkit-backface-visibility: hidden;
    backface-visibility: hidden;
}

.flip-card-front img,
.flip-card-back img {
    width: 100%;
    height: 100%;
}


.flip-card-back {
    transform: rotateY(180deg);
}
</style>