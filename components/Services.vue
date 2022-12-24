<template lang="pug">
.services
    h2 Наши услуги
    .services-wrapper 
        .service(v-for="service in services")
            .title {{ service.title }}
            .desc {{ service.desc }}
</template>

<script>
export default {
    name: 'ServicesBlock',
    data() {
        return{
            services: [
                {
                    title: 'Ведение от начала до конца',
                    desc: 'Контроль, управление, сопровождение посылки – отслеживаем отправку вашего товара поставщиком, комплектацию, упаковку на складе, отгрузку для транспортировки клиенту.'
                },
                {
                    title: 'Работа с поставщиками',
                    desc: 'Поиск самого подходящего поставщика по заданным клиентом параметрам товара.'
                },
                {
                    title: 'Выкуп товара',
                    desc: 'Выкуп товара с «Taobao.com», «Alibaba.com», оформление заказа, оплата товара.'
                },
                {
                    title: 'Инспекция товара',
                    desc: 'Инспекция товара включает в себя: количество, качество товара; соответствие модели и артикула товара; общий вес, объем; качество упаковки и т.д.'
                },
            ]
        }
    }

}
</script>

<style lang="scss">
.services{
    padding: 80px 0 80px 16px;
    background: #efefef;
    @media(min-width: 992px){
        padding: 120px 32px;
    }
    h2{
        margin-bottom: 24px;
        @media(min-width: 992px){
                text-align: center;
            }
    }
    .services-wrapper{
        display: flex;
        overflow: auto;
        @media(min-width: 992px){
            flex-wrap: wrap;
        }
        @media(min-width: 1200px){
            width: 1120px;
            margin: 0 auto;
            display: grid;
            grid-template-columns: 1fr 1fr;
        }
        .service{
            width: 300px;
            background: #fff;
            padding: 20px 15px;
            flex: 0 0 auto;
            border-radius: 10px;
            margin-right: 16px;
            @media(min-width: 992px){
                margin-right: 20px;
                margin-bottom: 20px;
            }
            @media(min-width: 1200px){
                width: auto;
            }
            .title{
                font-weight: 800;
                margin-bottom: 16px;
                font-size: 18px;
                padding-left: 20px;
                position: relative;
                &::before{
                    position: absolute;
                    content: '';
                    width: 5px;
                    height: 100%;
                    background: #36B5EB;
                    left: 0;
                    top: 0;
                }
            }
        }
    }

}
</style>