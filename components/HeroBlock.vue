<template lang="pug">
.hero
    .videohero
        .text
            h1 Доставляем грузы любой сложности из Китая
            p Качественный сервис и оптимальные решения поставленных задач
            //- a(href="#") Связаться
        video(src="~/assets/video/video.mp4" autoplay loop muted playsinline width="100%" height="100%")
</template>

<script>
export default {
    name: 'HeroBlock'
}
</script>

<style lang="scss" scoped>
.hero{
    margin-top: -95px;
    @media(min-width: 992px){
        margin-top: -120px;
    }
}
.videohero{
    position: relative;
    height: 600px;
    @media(min-width: 768px){
        height: 700px;
    }
    @media(min-width: 992px){
        height: 100vh;
    }
    video{
       position: absolute;
       z-index: -1;
       top: 0;
       object-fit: cover;
    }
    .text{
        width: 100%;
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        height: 100%;
        color: #fff;
        z-index: 3;
        padding: 16px;
        position: absolute;
        top: 0;
        h1{
            margin-bottom: 16px;
            text-align: center;
        }
        p{
             margin-bottom: 16px;
             text-align: center;
             font-size: 18px;
        }
        a{
            background:#0058BF;
            color: #fff;
            font-weight: 500;
            text-decoration: none;
            display: flex;
            align-items: center;
            justify-content: center;
            width: 200px;
            height: 50px;
            border-radius: 5px;            
        }
    }
    &:before{
        content: '';
        position: absolute;
        width: 100%;
        height: 100%;
        top: 0;
        background: rgb(25, 30, 40);
        opacity: 0.6;
        z-index: 2;
       }
}
</style>