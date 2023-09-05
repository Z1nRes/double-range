<template>
    <Slider 
    v-model="value" 
    :step="step" 
    :classes="classes"
    :max="max"
    list="list" />
    <datalist class="list">
        <option>2015</option>
        <option>фев</option>
        <option>мар</option>
        <option>апр</option>
        <option>май</option>
        <option>июн</option>
        <option>июл</option>
        <option>авг</option>
        <option>сен</option>
        <option>окт</option>
        <option>ноя</option>
        <option>дек</option>
        <option>2016</option>
        <option>фев</option>
        <option>мар</option>
        <option>апр</option>
        <option>май</option>
        <option>июн</option>
        <option>июл</option>
        <option>авг</option>
        <option>сен</option>
        <option>окт</option>
        <option>ноя</option>
        <option>дек</option>
        <option>2017</option>
    </datalist>
</template>
  
<script>
import Slider from '@vueform/slider'
export default {
    components: { Slider },
    data: () => ({
      value: [20, 100],
      step: 10,
      max: 250,
      classes: {
        vertical: 'slider-vertical',
      }
    }),
}
</script>

<style lang="scss">
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