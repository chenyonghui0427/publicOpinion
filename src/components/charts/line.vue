<!--线-->
<template>
    <div class="lineChart" v-loading="loading">
        <canvas :id="id" class="charts" />
    </div>
</template>

<script>
import F2 from "@antv/f2";
export default {
    props: {
        lineList: Array,
        id: String
    },
    data() {
        return {
            loading: false
        };
    },
    watch: {
        lineList: {
            handler: function() {}
        }
    },
    methods: {
        loadLineCharts(lists) {
            const data = lists;
            const chart = new F2.Chart({
                id: this.id,
                pixelRatio: window.devicePixelRatio
            });
            chart.source(data, {
                value: {
                    tickCount: 5,
                    min: 0
                },
                date: {
                    type: "timeCat",
                    range: [0, 1],
                    tickCount: 3
                }
            });
            chart.tooltip({
                custom: true,
                showXTip: true,
                showYTip: true,
                snap: true,
                crosshairsType: "xy",
                crosshairsStyle: {
                    lineDash: [2]
                }
            });
            chart.axis("date", {
                label: function label(text, index, total) {
                    const textCfg = {};
                    if (index === 0) {
                        textCfg.textAlign = "left";
                    } else if (index === total - 1) {
                        textCfg.textAlign = "right";
                    }
                    return textCfg;
                }
            });
            chart.line().position("date*value");
            chart.render();
        }
    },
    mounted() {
        let list = [
            {
                value: 77,
                city: "New York",
                date: "2011-10-01"
            },
            {
                value: 58,
                city: "New York",
                date: "2011-10-02"
            },
            {
                value: 33.3,
                city: "New York",
                date: "2011-10-03"
            },
            {
                value: 105.7,
                city: "New York",
                date: "2011-10-04"
            },
            {
                value: 164.2,
                city: "New York",
                date: "2011-10-05"
            },
            {
                value: 258.8,
                city: "New York",
                date: "2011-10-06"
            }
        ];
        this.loadLineCharts(list);
    }
};
</script>
<style scoped>
.lineChart {
    width: 100vw;
    height: 300rpx;
    background: #fff;
}
.charts {
    width: 100%;
    height: 100%;
}
</style>
