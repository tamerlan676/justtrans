<template lang="pug">
.scheme
    h2 Схема работы
    .scheme-wrapper 
        .step(v-for="step in scheme")
            .text {{ step.desc }}
</template>

<script>
export default {
    name: 'SchemeBlock',
    data() {
        return{
            scheme: [
                {
                    desc: '1. Оформление бланка заказа, включающего в себя все основные характеристики товара (изображение, количество, цвет, форма, размер и прочее).'
                },
                {
                    desc: '2. Подтверждение наличия заданных позиций у поставщиков; формирование перечня комментариев в бланке заказчика.'
                },
                {
                    desc: '3. Подтверждение наличия заданных позиций у поставщиков; формирование перечня комментариев в бланке заказчика.'
                },
                {
                    desc: '4. Оплата товара'
                },
                {
                    desc: '5. Выкуп товара'
                },
                {
                    desc: '6. Доставка по Китаю на наши склады, расположенные в таких городах как: Иву, Гуанджоу, Фошань, Пекин.'
                },
                {
                    desc: '7. Отправка товара получателю.'
                },
                {
                    desc: '8. Доставка до вашего города в России.'
                },
            ]
        }
    }

}
</script>

<style lang="scss">
.scheme{
    padding: 80px 16px;
    @media(min-width: 992px){
        padding: 120px 32px;
    }
    h2{
        margin-bottom: 24px;
        @media(min-width: 992px){
            text-align: center;
        }
    }
    .scheme-wrapper{
        @media(min-width: 992px){
            width: 100%;
            margin: 0 auto;
        }
        @media(min-width: 1200px){
            width: 1120px;
        }
        .step{
            position: relative;
            border-bottom: 1px solid rgb(235, 235, 235);
            padding: 16px 0;
            &::first-letter{
                color: #36B5EB;
                font-size: 18px;
                font-weight: 800;
            }
            @media(min-width: 992px){
                width: 800px;
                margin: 0 auto;
            }
        }
    }
}
</style>