<template>
  <div class="small">
    <!-- <horizontal-chart :chart-data="datacollection"></horizontal-chart> -->
    <horizontal-chart :chart-data="datacollection" :options="options"></horizontal-chart>
    <!-- <button @click="fillData()">Randomize</button> -->
  </div>
</template>

<script>
  // import LineChart from './LineChart.js'

  export default {
    // components: {
    //   LineChart
    // },
    data () {
      return {
      //   datacollection: [
      //     {
      //       label: 'Dataset 1',
      //       data: [40,20,10],
      //       // borderColor: Utils.CHART_COLORS.red,
      //       // backgroundColor: Utils.transparentize(Utils.CHART_COLORS.red, 0.5),
      //       borderColor: '#f87979',
      //       backgroundColor: '#f87979',
      //     },
      //     // {
      //     //   label: 'Dataset 2',
      //     //   data: Utils.numbers(NUMBER_CFG),
      //     //   // borderColor: Utils.CHART_COLORS.blue,
      //     //   backgroundColor: '#f87979',
      //     //   // backgroundColor: Utils.transparentize(Utils.CHART_COLORS.blue, 0.5),
      //     //   backgroundColor: '#f87979',
      //     // }
      //   ]
      // }
        // const labels = Utils.months({count: 7});
        // const data = {
        //   labels: labels,
        //   datasets: [{
        //     label: 'My First Dataset',
        //     data: [65, 59, 80, 81, 56, 55, 40],
            // backgroundColor: [
            //   'rgba(255, 99, 132, 0.2)',
            //   'rgba(255, 159, 64, 0.2)',
            //   'rgba(255, 205, 86, 0.2)',
            //   'rgba(75, 192, 192, 0.2)',
            //   'rgba(54, 162, 235, 0.2)',
            //   'rgba(153, 102, 255, 0.2)',
            //   'rgba(201, 203, 207, 0.2)'
            // ],
            // borderColor: [
            //   'rgb(255, 99, 132)',
            //   'rgb(255, 159, 64)',
            //   'rgb(255, 205, 86)',
            //   'rgb(75, 192, 192)',
            //   'rgb(54, 162, 235)',
            //   'rgb(153, 102, 255)',
            //   'rgb(201, 203, 207)'
            // ],
        //     borderWidth: 1
        //   }]
        // };
        datacollection: {
          labels: [
            'อนุมัติเลขที่กฏหมาย แต่เอกสารไม่พร้อมบอกกล่าว',
            'KTBLAW แจ้งเอกสารบอกกล่าวไม่ครบถ้วน / ไม่ถูกต้อง',
            'เอกสารครบถ้วน/ถูกต้อง แต่ยังไม่บอกกล่าว',
            'บอกกล่าวแล้ว',
            'ครบกำหนดบอกกล่าวแล้ว (เอกสารฟ้องครบถ้วน)',
            'เอกสารฟ้องไม่ครบถ้วน / ไม่ถูกต้อง',
            'ชะลอการดำเนินคดี',
          ],
          datasets: [{
            labels: 'MAIN TASK STATUS',
            data: [17, 8, 4, 0, 1, 6, 5],
            backgroundColor: [
              'rgba(255, 99, 132, 0.2)',
              'rgba(255, 159, 64, 0.2)',
              'rgba(255, 205, 86, 0.2)',
              'rgba(75, 192, 192, 0.2)',
              'rgba(54, 162, 235, 0.2)',
              'rgba(153, 102, 255, 0.2)',
              'rgba(201, 203, 207, 0.2)'
            ],
             borderColor: [
              'rgb(255, 99, 132)',
              'rgb(255, 159, 64)',
              'rgb(255, 205, 86)',
              'rgb(75, 192, 192)',
              'rgb(54, 162, 235)',
              'rgb(153, 102, 255)',
              'rgb(201, 203, 207)'
            ],
            borderWidth: 1
          }]
        },

        // datacollection: {
        //   labels: ['January', 'February', 'March', 'April', 'May', 'June', 'July', 'August', 'September', 'October', 'November', 'December'],
        //   datasets: [
        //     {
        //       label: 'Data One',
        //       backgroundColor: '#f87979',
        //       pointBackgroundColor: 'white',
        //       borderWidth: 1,
        //       pointBorderColor: '#249EBF',
        //       data: [40, 20, 30, 50, 90, 10, 20, 40, 50, 70, 90, 100]
        //     }
        //   ]
        // },
        options: {
          scales: {
            yAxes: [{
              ticks: {
                beginAtZero: true,
                callback: function(value, index, ticks) {
                  // return '$' + value;
                  return value;
                }
              },
              scaleLabel: {
                display: true,
                labelString: 'สถานะ',
                align: 'start',
                // maxRotation: 90,
                // minRotation: 90,
                // padding: {top: -5, left: 0, right: 0, bottom: 0}
              },
              gridLines: {
                display: true
              }
            }],
            xAxes: [{
              ticks: {
                beginAtZero: true
              },
              gridLines: {
                display: false
              },
              scaleLabel: {
                display: true,
                labelString: 'ราย',
                // padding: {top: 0, left: 0, right: 20, bottom: 0}
              },
            }]
          },
          legend: {
            display: false
          },
          tooltips: {
            enabled: true,
            mode: 'single',
            callbacks: {
              label: function(tooltipItems, data) {
                return '$' + tooltipItems.yLabel;
              }
            }
          },
          responsive: true,
          maintainAspectRatio: false,
          height: 200
        }
      }
    },
  }
</script>

<style>
  .small {
    max-width: 600px;
    margin:  150px auto;
  }
</style>