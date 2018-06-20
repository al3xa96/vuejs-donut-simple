<template>
  <section>
    <svg width="200px" height="200px" :viewBox=boxSize class="donut">
      <linearGradient id="hight_gradient" x1="0%" y1="0%" x2="100%" y2="0%">
          <stop offset="0%" :stop-color=hightContrastColorFirst stop-opacity="0.5" />
          <stop offset="100%" :stop-color=hightContrastColorSecond stop-opacity="0.5" />
      </linearGradient>
      <linearGradient id="low_gradient" x1="0%" y1="0%" x2="100%" y2="0%">
          <stop offset="0%" :stop-color=lowContrastColorFirst stop-opacity="0.5" />
          <stop offset="100%" :stop-color=lowContrastColorSecond stop-opacity="0.5" />
      </linearGradient>
      <circle class="donut-ring" cx="20" cy="20" :r="radio" fill="transparent" :stroke=baseColor
              :stroke-width="stroke"></circle>
      <circle v-if="percentage >= breakPoint"
              class="donut-segment" cx="20" cy="20" :r="radio"
              fill="transparent" stroke="url(#hight_gradient)" :stroke-width="stroke"
              :stroke-dasharray="percentage + ' ' + (100 - percentage)"
              stroke-dashoffset="0"></circle>
      <circle v-if="percentage < breakPoint"
              class="donut-segment" cx="20" cy="20" :r="radio"
              fill="transparent" stroke="url(#low_gradient)" :stroke-width="stroke"
              :stroke-dasharray="percentage + ' ' + (100 - percentage)"
              stroke-dashoffset="0"></circle>
      <g :style="'fill:' + fillColor" class="donut-quantity">
        <text x="34%" y="50%" class="donut-number">
          {{ percentage }}%
        </text>
        <text x="33%" y="75%" class="donut-label">
          {{ description }}
        </text>
      </g>
    </svg>
  </section>
</template>

<script>
export default {
  name: 'Donut',
  props: {
    percentage: {
      type: Number,
      required: true
    },
    description: {
      type: String,
      required: true
    },
    stroke: {
      type: Number,
      required: true
    },
    radio: {
      type: Number,
      required: false,
      default: 17
    },
    boxSize: {
      type: String,
      required: false,
      default: '-10 7 60 40'
    },
    breakPoint: {
      type: Number,
      required: false,
      default: 50
    },
    fillColor: {
      type: String,
      required: false,
      default: 'black'
    },
    baseColor: {
      type: String,
      required: false,
      default: '#DADADA'
    },
    hightContrastColorFirst: {
      type: String,
      required: false,
      default: '#00f315'
    },
    hightContrastColorSecond: {
      type: String,
      required: false,
      default: '#C0FF74'
    },
    lowContrastColorFirst: {
      type: String,
      required: false,
      default: '#fa0923'
    },
    lowContrastColorSecond: {
      type: String,
      required: false,
      default: '#ff5c70'
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  section {
    display: flex;
    flex-flow: row wrap;
    justify-items: center;
    align-content: space-around;
  }
  .donut-quantity {
    -moz-transform: translateY(0.25em);
    -ms-transform: translateY(0.25em);
    -webkit-transform: translateY(0.25em);
    transform: translateY(0.25em);
  }

  .donut-number {
    font-size: 0.7rem;
    font-weight: 600;
    font-family: Comfortaa, cursive;
    line-height: 1;
    text-anchor: middle;
  }

  .donut-label {
    font-size: 0.4em;
    text-transform: uppercase;
    text-anchor: middle;
    font-family: Comfortaa, sans-serif;
    -moz-transform: translateY(1rem);
    -ms-transform: translateY(1rem);
    -webkit-transform: translateY(1rem);
    transform: translateY(1rem);
  }
</style>
