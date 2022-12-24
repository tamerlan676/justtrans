<template lang="pug">
.header(:class="{change_color: scrollPosition > 50}")
    a(href="#")
        img(src="~/assets/images/logo.svg")
    //- .burder 
    //-     span
</template>

<script>
export default {
    name: 'HeaderComp',
    data() {
        return {
            scrollPosition: null
        }
    },
    mounted() {
    window.addEventListener('scroll', this.updateScroll);
    },
    methods: {
        updateScroll() {
       this.scrollPosition = window.scrollY
        }
    }

}
</script>

<style lang="scss">
    .header{
        width: 100%;
        height: 95px;
        z-index: 100;
        position: sticky;
        padding: 16px;
        display: flex;
        align-items: center;
        justify-content: space-between;
        overflow: hidden;
        box-sizing: border-box;
        transition: all .3s linear;
        top: 0;
        @media(min-width: 992px){
            padding: 32px;
            height: 120px;
        }
        a{
            display: block;
        }
        img{
            width: 120px;
            @media(min-width: 992px){
                width: 150px;
            }
        }
        .burder{
            width: 30px;
            height: 20px;
            position: relative;
            &:before{
                position: absolute;
                content: '';
                width: 30px;
                height: 2px;
                background: rgb(75, 163, 231);
                top: 0;
            }
            &:after{
                position: absolute;
                content: '';
                width: 30px;
                height: 2px;
                background: rgb(75, 163, 231);
                bottom: 0;
            }
            span{
                position: absolute;
                content: '';
                width: 30px;
                height: 2px;
                background: rgb(75, 163, 231);
                top:9px;
            }
        }   
    }
    .change_color {
        background: #fff 
    } 

</style>