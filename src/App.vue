<template>
  <div id="app">
    <donut :percentage="percentage"
           :description="name"
           :stroke="stroke"
           :radio="radio"
           :breakPoint="breakPoint"
           :fillColor="fillColor"
          ></donut>
  </div>
</template>

<script>
import donut from './components/donutChart'

export default {
  name: 'App',
  data () {
    return {
      percentage: 45,
      name: 'Donut Value',
      stroke: 7,
      radio: 17,
      breakPoint: 50,
      fillColor: '#808080'
    }
  },
  components: {
    donut
  }
}
</script>

<style>
#app {
  font-family: 'Comfortaa', cursive;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #393250;
  margin-top: 60px;
}
</style>
