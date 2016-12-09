<template>
  <input type="text">
</template>

<script>
import Chart from 'chart.js'
import _ from 'lodash'

export default {
  name: 'query-input',

  data () {
    return {
      chart: null
    }
  },

  props: [ 'query' ],

  mounted () {
    // Data format: 
    // { label: '...', value: '...', color: '#...' }
    let labels = _.map(this.data, d => d.label)
    let values = _.map(this.data, d => d.value)
    let bgColors = _.map(this.data, d => d.color)
    let donutData = {
      labels,
      datasets: [{
        data: values, backgroundColor: bgColors
      }]
    }
    console.log(donutData)
    this.chart = new Chart(this.id, {
      type: 'doughnut',
      data: donutData
    })
  }
}
</script>
