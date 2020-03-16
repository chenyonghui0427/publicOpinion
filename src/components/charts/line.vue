<template>
    <div class="lineChart" v-loading="loading">
        <canvas id="container" />
        <!-- <div>{{list.length}}</div> -->
    </div>
</template>

<script>
import F2 from "@antv/f2";
export default {
    props: {
        lineList: Array
    },
    data() {
        return {
            loading: true
        };
    },
    watch: {
        lineList: {
            handler: function() {
                let list = [
                    {
                        value: 63.4,
                        city: "New York",
                        date: "2011-10-01"
                    },
                    {
                        value: 62.7,
                        city: "Alaska",
                        date: "2011-10-01"
                    },
                    {
                        value: 72.2,
                        city: "Austin",
                        date: "2011-10-01"
                    },
                    {
                        value: 58,
                        city: "New York",
                        date: "2011-10-02"
                    },
                    {
                        value: 59.9,
                        city: "Alaska",
                        date: "2011-10-02"
                    },
                    {
                        value: 67.7,
                        city: "Austin",
                        date: "2011-10-02"
                    },
                    {
                        value: 53.3,
                        city: "New York",
                        date: "2011-10-03"
                    },
                    {
                        value: 59.1,
                        city: "Alaska",
                        date: "2011-10-03"
                    },
                    {
                        value: 69.4,
                        city: "Austin",
                        date: "2011-10-03"
                    },
                    {
                        value: 55.7,
                        city: "New York",
                        date: "2011-10-04"
                    },
                    {
                        value: 58.8,
                        city: "Alaska",
                        date: "2011-10-04"
                    },
                    {
                        value: 68,
                        city: "Austin",
                        date: "2011-10-04"
                    },
                    {
                        value: 64.2,
                        city: "New York",
                        date: "2011-10-05"
                    },
                    {
                        value: 58.7,
                        city: "Alaska",
                        date: "2011-10-05"
                    },
                    {
                        value: 72.4,
                        city: "Austin",
                        date: "2011-10-05"
                    },
                    {
                        value: 58.8,
                        city: "New York",
                        date: "2011-10-06"
                    }
                ];
                this.loadLineCharts(list);
            }
        }
    },
    methods: {
        text() {
            console.log("text");
        },
        loadLineCharts(lists) {
            const data = lists;
            const chart = new F2.Chart({
                id: "container",
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
            chart.line().position("city*date");
            chart.render();
        }
    },
    mounted() {
        let list = [
            {
                value: 1234.4,
                city: "New York",
                date: "2011-10-01"
            },
            {
                value: 123.7,
                city: "Alaska",
                date: "2011-10-01"
            },
            {
                value: 4124.2,
                city: "Austin",
                date: "2011-10-01"
            },
            {
                value: 12312,
                city: "New York",
                date: "2011-10-02"
            },
            {
                value: 21312.9,
                city: "Alaska",
                date: "2011-10-02"
            },
            {
                value: 1231.7,
                city: "Austin",
                date: "2011-10-02"
            },
            {
                value: 12312.3,
                city: "New York",
                date: "2011-10-03"
            },
            {
                value: 123421.1,
                city: "Alaska",
                date: "2011-10-03"
            },
            {
                value: 69.4,
                city: "Austin",
                date: "2011-10-03"
            },
            {
                value: 123123.7,
                city: "New York",
                date: "2011-10-04"
            },
            {
                value: 125435.8,
                city: "Alaska",
                date: "2011-10-04"
            },
            {
                value: 324123,
                city: "Austin",
                date: "2011-10-04"
            },
            {
                value: 432.2,
                city: "New York",
                date: "2011-10-05"
            },
            {
                value: 58.7,
                city: "Alaska",
                date: "2011-10-05"
            },
            {
                value: 72.4,
                city: "Austin",
                date: "2011-10-05"
            },
            {
                value: 58.8,
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
}
#container {
    width: 100%;
    height: 100%;
}
</style>
