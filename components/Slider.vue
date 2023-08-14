<template lang="pug">
.slider
    agile(arrows="false")
        div.slide(v-for="(slide, index) in slides", :key="index", :class="`slide--${index}`")
                img(:src="slide")

    agile.thumbnails(ref="thumbnails" :options="options2" :as-nav-for="asNavFor2")
        div.slide.slide--thumbniail(v-for="(slide, index) in slides", :key="index", :class="`slide--${index}`" @click="$refs.thumbnails.goTo(index)")
            img(:src="slide")

        template(slot="prevButton")
            i.fas.fa-chevron-left
        template(slot="nextButton")
            i.fas.fa-chevron-right
</template>

<script>
import { VueAgile } from 'vue-agile'

export default {
    name: 'SliderComp',
    components: {
        agile: VueAgile
    },
    data() {
        return{
            text: 'Транспортная компания «JUSTTRANS» ведет свою историю с 2015 года. \n Опыт компании позволяет осуществлять поставки быстро, освобождая клиентов от задач, связанных с поиском товара, волнений за сохранность и целостность поставок. \n\n Компания гарантирует быструю доставку грузов и адекватную ценовую политику. \n\n Наличие представительств, курирующих логистику на территории Китая, Казахстана и России позволяет отслеживать маршрут грузов на каждом этапе. Мы осуществляем доставку грузов в течении 15-25 рабочих дней.',
            slides: [
					'https://images.unsplash.com/photo-1453831362806-3d5577f014a4?ixlib=rb-1.2.1&q=85&fm=jpg&crop=entropy&cs=srgb&w=1600&fit=max&ixid=eyJhcHBfaWQiOjE0NTg5fQ',
					'https://images.unsplash.com/photo-1496412705862-e0088f16f791?ixlib=rb-1.2.1&q=85&fm=jpg&crop=entropy&cs=srgb&w=1600&fit=max&ixid=eyJhcHBfaWQiOjE0NTg5fQ',
					'https://images.unsplash.com/photo-1506354666786-959d6d497f1a?ixlib=rb-1.2.1&q=85&fm=jpg&crop=entropy&cs=srgb&w=1600&fit=max&ixid=eyJhcHBfaWQiOjE0NTg5fQ',
					'https://images.unsplash.com/photo-1455619452474-d2be8b1e70cd?ixlib=rb-1.2.1&q=85&fm=jpg&crop=entropy&cs=srgb&w=1600&fit=max&ixid=eyJhcHBfaWQiOjE0NTg5fQ',
					'https://images.unsplash.com/photo-1504674900247-0877df9cc836?ixlib=rb-1.2.1&q=85&fm=jpg&crop=entropy&cs=srgb&w=1600&fit=max&ixid=eyJhcHBfaWQiOjE0NTg5fQ',
					'https://images.unsplash.com/photo-1472926373053-51b220987527?ixlib=rb-1.2.1&q=85&fm=jpg&crop=entropy&cs=srgb&w=1600&fit=max&ixid=eyJhcHBfaWQiOjE0NTg5fQ',
					'https://images.unsplash.com/photo-1497534547324-0ebb3f052e88?ixlib=rb-1.2.1&q=85&fm=jpg&crop=entropy&cs=srgb&w=1600&fit=max&ixid=eyJhcHBfaWQiOjE0NTg5fQ'
				],
            asNavFor1: [],
			asNavFor2: [],
			options1: {
				dots: false,
				fade: true,
				navButtons: false
			},
			
			options2: {
				autoplay: true,
				centerMode: true,
				dots: false,
				navButtons: false,
				slidesToShow: 3,
				responsive: [
                {
                    breakpoint: 600,
                    settings: {
                        slidesToShow: 5
                    }
                },
                
                {
                    breakpoint: 1000,
                    settings: {
                        navButtons: true
                    }
                }
            ]
				
			},
        }
    },
    mounted () {
		this.asNavFor1.push(this.$refs.thumbnails)
		this.asNavFor2.push(this.$refs.main)
	}

}
</script>

<style lang="scss">
  
  .main {
    margin-bottom: 30px;
  }
  
  .thumbnails {
    margin: 0 -5px;
    width: calc(100% + 10px);
  }
  
  .agile__nav-button {
    background: transparent;
    border: none;
    color: #ccc;
    cursor: pointer;
    font-size: 24px;
    transition-duration: 0.3s;
  }
  .thumbnails .agile__nav-button {
    position: absolute;
    top: 50%;
    transform: translateY(-50%);
  }
  .thumbnails .agile__nav-button--prev {
    left: -45px;
  }
  .thumbnails .agile__nav-button--next {
    right: -45px;
  }
  .agile__nav-button:hover {
    color: #888;
  }
  .agile__dot {
    margin: 0 10px;
  }
  .agile__dot button {
    background-color: #eee;
    border: none;
    border-radius: 50%;
    cursor: pointer;
    display: block;
    height: 10px;
    font-size: 0;
    line-height: 0;
    margin: 0;
    padding: 0;
    transition-duration: 0.3s;
    width: 10px;
  }
  .agile__dot--current button, .agile__dot:hover button {
    background-color: #888;
  }
  
  .slide {
    align-items: center;
    box-sizing: border-box;
    color: #fff;
    display: flex;
    height: 450px;
    justify-content: center;
  }
  .slide--thumbniail {
    cursor: pointer;
    height: 100px;
    padding: 0 5px;
    transition: opacity 0.3s;
  }
  .slide--thumbniail:hover {
    opacity: 0.75;
  }
  .slide img {
    height: 100%;
    -o-object-fit: cover;
       object-fit: cover;
    -o-object-position: center;
       object-position: center;
    width: 100%;
  }
</style>