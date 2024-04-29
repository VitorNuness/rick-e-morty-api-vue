<script setup>
let character = defineProps([
    "imgUrl",
    "name",
    "status",
    "specie",
    "gender",
    "location",
    "episodesTotal",
]);
</script>

<template>
    <div class="col-md-6 col-sm-12 col-lg-3">
        <div class="flip-card">
            <div class="flip-card-inner">
                <div class="flip-card-front">
                    <img
                        :src="character.imgUrl"
                        :alt="character.name"
                        class="card-front-img"
                    />
                    <h5 class="card-title">{{ character.name }}</h5>
                </div>
                <div class="flip-card-back">
                    <img
                        :src="character.imgUrl"
                        :alt="character.name"
                        width="60rem"
                        class="card-back-img"
                    />
                    <h6>{{ character.name }}</h6>
                    <p>
                        <img
                            src="../assets/transgender-solid.svg"
                            alt="Ícone transgênero"
                            style="width: 1rem"
                        />
                        {{ character.gender }}
                    </p>
                    <p>
                        <img
                            src="../assets/heart-pulse-solid.svg"
                            alt="Ícone batimento cardíaco"
                            style="width: 1rem"
                        />
                        {{ character.status }}
                    </p>
                    <p>
                        <img
                            src="../assets/dna-solid.svg"
                            alt="Ícone DNA"
                            style="width: 1rem"
                        />
                        {{ character.specie }}
                    </p>
                    <p>
                        <img
                            src="../assets/location-dot-solid.svg"
                            alt="Ícone localização"
                            style="width: 1rem"
                        />
                        {{ character.location }}
                    </p>
                    <p>
                        <img
                            src="../assets/eye-solid.svg"
                            alt="Ícone olho"
                            style="width: 1rem"
                        />
                        {{ character.episodesTotal }}
                    </p>
                </div>
            </div>
        </div>
    </div>
</template>

<style lang="css">
.flip-card {
    background-color: transparent;
    height: 25rem;
    text-align: center;
    margin-bottom: 20px;
}

.flip-card-inner {
    border-radius: 10px;
    border: 1px solid #5bff0f;
    height: 100%;
    transition: transform 0.8s;
    transform-style: preserve-3d;
}

.flip-card:hover .flip-card-inner {
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

.flip-card-front {
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    padding-bottom: 20px;
}

.flip-card-back {
    border-radius: 10px;
    border: 1px solid #5bff0f;
    background: #529eca;
    color: #fff;
    padding-top: 20px !important;
    padding: 0px 30px;
    transform: rotateY(180deg);
}

.card-front-img {
    border-radius: 10px 10px 0px 0px;
    width: 100%;
}

.card-back-img {
    border-radius: 50%;
    margin-bottom: 20px;
}
</style>
