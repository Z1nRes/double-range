<template>
    <Slider 
    v-model="value" 
    :step="step" 
    :classes="classes"
    :max="max"
    list="list" />
    <datalist class="list">
        <option>2014</option>
        <option>2015</option>
        <option>2016</option>
        <option>2017</option>
        <option>2018</option>
        <option>2019</option>
        <option>2020</option>
        <option>2021</option>
    </datalist>
</template>
  
<script>
import Slider from '@vueform/slider'
export default {
    components: { Slider },
    data: () => ({
      value: [20, 40],
      step: 10,
      max: 80,
      classes: {
        vertical: 'slider-vertical',
      }
    }),
}
</script>

<style lang="scss" scoped>
    @import '../../node_modules/@vueform/slider/themes/default.scss';

    :root{
        --slider-bg: #EDF1F8;
        --slider-connect-bg: #5CADEA;

        --slider-handle-border: 4px solid #5CADEA;

        --slider-tooltip-bg: #EDF1F8;
        --slider-tooltip-color: #0167B3;
    }
    .slider-handle-upper .slider-tooltip-top:nth-child(2){
        transform: rotate(180deg) translate(50%) !important;
        bottom: calc(var(--slider-handle-height, -16px) + var(--slider-tooltip-arrow-size, -22px) + var(--slider-tooltip-distance, -3px)) !important;
    }
    .list{
    display: flex;
    position: relative;
    justify-content: space-between;
    height: auto;
    overflow: hidden;
    margin-top: 16px; 
    width: 100%;
    left: -5px;
    }
</style>