<script>
import { Doughnut, mixins } from 'vue-chartjs'
const { reactiveProp } = mixins

const plugin = function(chart) {
  var width = chart.chart.width;
  var height = chart.chart.height;
  var ctx = chart.chart.ctx;

  ctx.restore();
  // var fontSize = (height / 114).toFixed(2);
  var fontSize = (height / 400).toFixed(2);
  ctx.font = fontSize + "em sans-serif";
  ctx.textBaseline = "middle";

  // var text = 800;
  var num = 77;
  // var text = `รวมทั้งสิ้น\n${num}\nเลขที่กฏหมาย`;
  var text = 'รวมทั้งสิ้น\n77\nเลขที่กฏหมาย';
  // var textX = Math.round((width - ctx.measureText(text).width) / 2);
  // var textY = height / 2;
  var lineheight = 30;

  var lines = text.split('\n');
  for (var i = 0; i<lines.length; i++) {
    var textX = Math.round((width - ctx.measureText(lines[i]).width) / 2);
    var textY = height / 2;

    ctx.fillText(lines[i], textX, textY + (i*lineheight));
  }
    // ctx.fillText(text, textX, textY);
    //  c.fillText(lines[i], x, y + (i*lineheight));
  ctx.save();
}

export default {
  extends: Doughnut,
  mixins: [reactiveProp],
  props: ['options'],
  mounted () {
    this.addPlugin({
      id: 'my-plugin',
      // beforeDraw: function(chart) {}
      beforeDraw: plugin
    })
    // this.chartData is created in the mixin.
    // If you want to pass options please create a local options object
    this.renderChart(this.chartData, this.options)
  }
}
</script>