<template>
    <div class="mt-5 container hero ">
            <h1 class="title has-text-centered has-text-weight-semibold">Pixabay All Photos</h1>
            <div class="has-text-centered control" >
                <input type="text" class="input " style="max-width: 300px;">
                <button class="button is-primary ml-3">Search</button>
            </div>
    <div class="columns mt-5 box ">
        <div class="column is-4 block">
            <div class="card px-3 p-2">
                <h4 class="has-text-centered title">Kirubel</h4>
                <img src="https://pixabay.com/get/gaee700e470a220ef999aaa32b45a8577cdd8b62ab022f145e76fcd9095e772653fcd199c5b3fa77aea95318d5d324d26e44b2dc6de901c27c520c257dd95351d_1280.jpg" alt="">
                <div class="card-content">
                    <div class="media">
                        <div class="media-left">
                            <figure class="image is-64x64 ">
                                <img src="https://cdn.pixabay.com/user/2018/05/28/23-31-09-916_250x250.jpg" alt="" class="is-rounded">
                            </figure>
                        </div>
                        <div class="media-content">
                            <p class="is-4 title">Kirubel</p>
                            <p class="subtitle is-6">@kirubel</p>
                        </div>
                    </div>
                    <div class="content">
                        <p class="tag is-primary">Cat</p> <p class="tag is-primary">Catty</p>
                    </div>
                    <footer class="card-footer mt-5">
                    <div class="mt-3">
                        <p class="subtitle is-info">Likes - 100</p>
                        <p class="subtitle">Download - 100</p>
                        <p class="subtitle">Views - 100</p>
                    </div>
                    </footer>

                </div>
            </div>
        </div>
        <div class="column is-4 ">
            <div class="card px-3 p-2">
                <h4 class="has-text-centered title">Kirubel</h4>
                <img src="https://pixabay.com/get/gaee700e470a220ef999aaa32b45a8577cdd8b62ab022f145e76fcd9095e772653fcd199c5b3fa77aea95318d5d324d26e44b2dc6de901c27c520c257dd95351d_1280.jpg" alt="">
                <div class="card-content">
                    <div class="media">
                        <div class="media-left">
                            <figure class="image is-64x64 ">
                                <img src="https://cdn.pixabay.com/user/2018/05/28/23-31-09-916_250x250.jpg" alt="" class="is-rounded">
                            </figure>
                        </div>
                        <div class="media-content">
                            <p class="is-4 title">Kirubel</p>
                            <p class="subtitle is-6">@kirubel</p>
                        </div>
                    </div>
                    <div class="content">
                        <p class="tag is-primary">Cat</p> <p class="tag is-primary">Catty</p>
                    </div>
                    <footer class="card-footer mt-5">
                    <div class="mt-3">
                        <p class="subtitle is-info">Likes - 100</p>
                        <p class="subtitle">Download - 100</p>
                        <p class="subtitle">Views - 100</p>
                    </div>
                    </footer>

                </div>
            </div>
        </div>
        <div class="column is-4 ">
            <div class="card px-3 p-2">
                <h4 class="has-text-centered title">Kirubel</h4>
                <img src="https://pixabay.com/get/gaee700e470a220ef999aaa32b45a8577cdd8b62ab022f145e76fcd9095e772653fcd199c5b3fa77aea95318d5d324d26e44b2dc6de901c27c520c257dd95351d_1280.jpg" alt="">
                <div class="card-content">
                    <div class="media">
                        <div class="media-left">
                            <figure class="image is-64x64 ">
                                <img src="https://cdn.pixabay.com/user/2018/05/28/23-31-09-916_250x250.jpg" alt="" class="is-rounded">
                            </figure>
                        </div>
                        <div class="media-content">
                            <p class="is-4 title">Kirubel</p>
                            <p class="subtitle is-6">@kirubel</p>
                        </div>
                    </div>
                    <div class="content">
                        <p class="tag is-primary">Cat</p> <p class="tag is-primary">Catty</p>
                    </div>
                    <footer class="card-footer mt-5">
                    <div class="mt-3">
                        <p class="subtitle is-info">Likes - 100</p>
                        <p class="subtitle">Download - 100</p>
                        <p class="subtitle">Views - 100</p>
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
        photos.value = PixabayPhotos
        console.log(photos.hits)
    })
}
getData()
</script>

<style scoped>

</style>