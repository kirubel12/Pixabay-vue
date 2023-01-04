<template>
    <div class="mt-5 container hero ">
            <h1 class="title has-text-centered has-text-weight-semibold">Pixabay All Photos</h1>
            <div class="has-text-centered control" >
                <input type="text" class="input " style="max-width: 300px;">
                <button class="button is-primary ml-3">Search</button>
            </div>
    <div class="columns mt-5 box" v-for="picture in PixabayPhotos">
        <div class="column is-4 ">
            <div class="card px-3 p-2">
                <h4 class="has-text-centered title">{{ picture.type }}</h4>
                <img :src="picture.largeImageURL" alt="">
                <div class="card-content">
                    <div class="media">
                        <div class="media-left">
                            <figure class="image is-64x64 ">
                                <img :src="picture.userImageURL" alt="" class="is-rounded">
                            </figure>
                        </div>
                        <div class="media-content">
                            <p class="is-4 title">{{ picture.user }}</p>
                            <p class="subtitle is-6">@ {{ picture.user_id }}</p>
                        </div>
                    </div>
                    <div class="content" v-for="tag in picture.tags">
                    
                    </div>
                    <footer class="card-footer mt-5">
                    <div class="mt-3">
                        <p class="subtitle is-info">Likes - {{ picture.likes }}</p>
                        <p class="subtitle">Download - {{ picture.downloads }}</p>
                        <p class="subtitle">Views - {{ picture.views }}</p>
                    </div>
                    </footer>

                </div>
            </div>
        </div>
    </div>
    </div>
   
</template>

<script setup>
import {ref} from 'vue'
const PixabayPhotos = ref([]);
const url = "https://pixabay.com/api/?key=12390348-c8e06852d0a0011ced6af954c"
async function getData(){
    await fetch(url)
    .then((res) => res.json())
    .then((photos) => {
        PixabayPhotos.value = photos.hits
        console.log(photos)
    })
}
getData()
</script>

<style scoped>

</style>