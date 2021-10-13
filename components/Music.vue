<template>
  <b-card style="height:300px;width: 260px" class="card-music pb-3">
        <div class="card-img">
            <img :src="data.cover_big" alt="">
            <div style="width: 80%">
                <p class="title1">{{data.title}}</p>
                <p class="title2">{{data.name}}</p>
            </div>
        </div>
        <b-card-body class="name_album px-3 pt-2 d-flex justify-content-between">
            <div class="d-flex flex-column">
                <p class="mb-0 text-white font-weight-bold">Album</p>
                <p style="font-size:13px" class="mb-0 text-white">{{data.title_album}}</p>
            </div>
            <div class="d-flex justify-content-center align-items-center">
                <b-button class="btn-play rounded-circle">
                    <b-icon icon="play"></b-icon>
                </b-button>
            </div>
        </b-card-body>
  </b-card>
</template>

<script>
export default {
    props:['data']
}
</script>

<style scoped>

.name_album{
    overflow: hidden;
    white-space: nowrap;
    width: 90%;
    text-overflow: ellipsis;
}

img{
    width: 100%;
    height: 100%;
    border-radius: 15px;
}

.card-body{
    padding: 0;
}

.card-music{
    position: relative;
    display: flex;
    flex-direction: column;
    min-width: 250px;
    word-wrap: break-word;
    background-color: #1B1919;
    background-clip: border-box;
    border: 1px solid rgba(0, 0, 0, 0.125);
    border-radius: 15px;
    padding:5px
}

.card-img{
    text-overflow: ellipsis;
    white-space: nowrap;
    overflow: hidden;
    height:80%;
    position:relative;
    display: inline-block;
}

.title1,
.title2{
    position: absolute;
    
    color: white;
    font-size: 20px;
    font-weight: bold;
}

.title1{
    top: 75%;
    left: 5%;
}

.title2{
    top: 84%;
    left: 10%;
}

.btn-play{
    height: 30px;
    width: 30px;
    display: flex;
    justify-content: center;
    align-items: center;
}

</style>