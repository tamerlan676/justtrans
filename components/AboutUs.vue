<template lang="pug">
.about
    .about-wrapper
        .info
            h2 О Нас
            p {{ text }}
        .image
            img(src="~/assets/images/about.webp")
</template>

<script>
export default {
    data() {
        return{
            text: 'Транспортная компания «JUSTTRANS» ведет свою историю с 2015 года. \n Опыт компании позволяет осуществлять поставки быстро, освобождая клиентов от задач, связанных с поиском товара, волнений за сохранность и целостность поставок. \n\n Компания гарантирует быструю доставку грузов и адекватную ценовую политику. \n\n Наличие представительств, курирующих логистику на территории Китая, Казахстана и России позволяет отслеживать маршрут грузов на каждом этапе. Мы осуществляем доставку грузов в течении 15-25 рабочих дней.'
        }
    }

}
</script>

<style lang="scss">
.about{
    width: 100%;
    padding: 80px 16px;
    @media(min-width: 992px){
        padding: 120px 32px;
    }
    .about-wrapper{
        @media(min-width: 992px){
            display: flex;
            margin: 0 auto;
            align-items: center;
        }
        @media(min-width: 1200px){
            width: 1120px;
        }
        .info{
            margin-bottom: 24px;
            @media(min-width: 992px){
                margin-right: 20px;
                width: 70%;
            }
        h2{
            margin-bottom: 24px;
            }
        p{
            white-space: pre-line;
        }
    }
    .image{
        width: 100%;
        img{
            max-width: 100%;
        }
    }
    }
}

</style>