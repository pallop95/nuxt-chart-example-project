<template>
  <div class="small">
    <doughnut-chart :chart-data="datacollection"></doughnut-chart>
    <button @click="fillData()">Randomize</button>
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
        datacollection: {
          labels: [
            "อนุมัติดำเนินคดี", 
            "ยึดทรัพย์", 
            "ฟื้นฟูกิจการ", 
            "ฟ้องแล้ว/พิพากษา",
            "อยู่ระหว่างขายทอดตลาด",
            "ล้มละลาย",
            "คดียื่นขอรับชำระหนี้บุริมสิทธิจำนอง",
          ],
          datasets: [
            {
              label: "Data One",
              backgroundColor: ["#a3c7c9", "#889d9e", "#647678", "f87979"],
              data: [60, 13, 18, 13, 17, 15,41]
            }
          ]
        },
        // datacollection: {
        //   labels: ["Cambodia", "Thailand", "Vietnam", "Laos"],
        //   datasets: [
        //     {
        //       label: "Data One",
        //       backgroundColor: ["#a3c7c9", "#889d9e", "#647678", "f87979"],
        //       data: [91, 3, 3, 3]
        //     }
        //   ]
        // },
        options: {
          legend: {
            display: false
          },
          pieceLabel: {
            mode: 'value'
          },
          responsive: true,
          maintainAspectRatio: false,
          
        }
      }
    },
    mounted () {
      this.fillData()
    },
    methods: {
      fillData () {
        // this.datacollection = {
        //   // labels: [this.getRandomInt(), this.getRandomInt()],
        //   // datasets: [
        //   //   {
        //   //     label: 'Data One',
        //   //     backgroundColor: '#f87979',
        //   //     data: [this.getRandomInt(), this.getRandomInt()]
        //   //   }, {
        //   //     label: 'Data One',
        //   //     backgroundColor: '#f87979',
        //   //     data: [this.getRandomInt(), this.getRandomInt()]
        //   //   }
        //   // ]
        //   labels: ["Cambodia", "Thailand", "Vietnam", "Laos"],
        //   datasets: [
        //     {
        //       label: "Data One",
        //       backgroundColor: ["#a3c7c9", "#889d9e", "#647678", "f87979"],
        //       data: [91, 3, 3, 3]
        //     }
        //   ]
        // }
      },
      getRandomInt () {
        return Math.floor(Math.random() * (50 - 5 + 1)) + 5
      }
    }
  }
</script>

<style>
  .small {
    max-width: 600px;
    margin:  150px auto;
  }
</style>