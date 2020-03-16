<template>
    <div class="home">
        <div class="content">
            <LineCharts  :lineList="lineList"/>
            <canvas id="myChart"></canvas>
            <div @click="change">change</div>
        </div>
    </div>
</template>

<script>
const F2 = require("@antv/f2");
import LineCharts from "@/components/charts/line";
export default {
    components: {
        LineCharts
    },
    data() {
        return {
            data: [
                { genre: "Sports", sold: 275 },
                { genre: "Strategy", sold: 115 },
                { genre: "Action", sold: 120 },
                { genre: "Shooter", sold: 350 },
                { genre: "Other", sold: 150 }
            ],
            lineList:[1,2,3,4,5]
        };
    },
    methods: {
        change(){
            this.lineList=[1,2,3,4,5,4,3,2,1]
        },
        load() {
            var that = this;
            const chart = new F2.Chart({
                id: "myChart",
                pixelRatio: window.devicePixelRatio // 指定分辨率
            });
            // Step 2: 载入数据源
            chart.source(that.data);

            // Step 3：创建图形语法，绘制柱状图，由 genre 和 sold 两个属性决定图形位置，genre 映射至 x 轴，sold 映射至 y 轴
            chart
                .interval()
                .position("genre*sold")
                .color("genre");

            // Step 4: 渲染图表
            chart.render();
        }
    },
    mounted() {
        this.load();

        const e = document.createEvent("Event");
        e.initEvent("resize", true, true);
        window.dispatchEvent(e);
    }
};
</script>
<style scoped>
.content {
    width: 100vw;
    /* background: red; */
    margin: 0 auto;
    box-sizing: border-box;
}
#myChart {
    width: 100%;
    /* height: 5rem; */
}
</style>
