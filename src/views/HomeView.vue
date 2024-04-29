<script setup>
import { onMounted, reactive, ref } from "vue";
import CharactersList from "../components/CharactersList.vue";

let charactersCount = reactive(ref());
let characters = reactive(ref());
let list = [];

onMounted(() => {
    fetch("https://rickandmortyapi.com/api/character")
        .then((res) => res.json())
        .then((res) => {
            charactersCount.value = res.info.count;

            for (let i = 1; i <= charactersCount.value + 1; i++) {
                list.push(i);
            }
            fetch(`https://rickandmortyapi.com/api/character/${list}`)
                .then((res) => res.json())
                .then((res) => {
                    characters.value = res;
                });
        });
});
</script>

<template>
    <main>
        <div class="container">
            <div class="row mt-4">
                <div class="card">
                    <div class="card-body row">
                        <CharactersList
                            v-for="character in characters"
                            :key="character.id"
                            :img-url="character.image"
                            :name="character.name"
                            :status="character.status"
                            :specie="character.species"
                            :gender="character.gender"
                            :location="character.location.name"
                            :episodes-total="character.episode.length"
                        />
                    </div>
                </div>
            </div>
        </div>
    </main>
</template>

<style>
.card {
    border: 1px solid #5bff0f;
}
</style>
