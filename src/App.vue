<template>
  <div class="wrapper-slider">
    <div class="btn-toogle">
      <span class="span span-active" @click="toogle">Все года</span>
      <span class="span">Месяца</span>
    </div>
    <div class="slider" v-if="type === 'years'">
      <DoubleSliderYears/>
    </div>
    <div class="slider" v-else>
      <DoubleSliderMonths/>
    </div> 
  </div>
</template>

<script>
import DoubleSliderYears from './components/DoubleSliderYears.vue';
import DoubleSliderMonths from './components/DoubleSliderMonths.vue';

export default {
  name: 'App',
  components: {DoubleSliderYears, DoubleSliderMonths},
  data() {
    return{
      type: 'years',
    }
  },
  methods: {
    toogle() {
      if (this.type === 'years'){
        this.type = 'month'
      } else {
        this.type = 'years'
      }
      const span = document.querySelectorAll('.span')
      if(span[0].className === 'span span-active') {
        span[0].className = 'span'
        span[1].className = 'span span-active'
      } else {
        span[1].className = 'span'
        span[0].className = 'span span-active'
      }
    }
  }
}
</script>

<style>
body {
  font-family: Avenir, Helvetica, Arial, sans-serif;
}
#app {
  margin-top: 60px;
  padding: 20px;
  width: 100em;
} 

.wrapper-slider{
  width: 70em;
  padding-left: 4em;
  display: flex;
}

.btn-toogle{
  display: flex;
  flex-direction: column;
  align-items: start;
  cursor: pointer;
  margin-right: 7em;
  height: 43px !important;
}
.span {
  color: #0167B3;
  opacity: 0.5;
  width: 65px;
}
.slider{
  width: 50em;
}
.span-active {
  opacity: 1 !important;
}
</style>
