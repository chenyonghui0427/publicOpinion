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
                sales: {
                    tickCount: 5
                }
            });
            chart.tooltip({
                showItemMarker: false,
                onShow: function onShow(ev) {
                    const items = ev.items;
                    items[0].name = null;
                    items[0].name = items[0].title;
                    items[0].value = "¥ " + items[0].value;
                }
            });
            chart.interval().position("year*sales");
            chart.render();
        }
    },
    mounted() {
        let list = [
            {
                year: "1951 年",
                sales: 38
            },
            {
                year: "1952 年",
                sales: 52
            },
            {
                year: "1956 年",
                sales: 61
            },
            {
                year: "1957 年",
                sales: 145
            },
            {
                year: "1958 年",
                sales: 48
            },
            {
                year: "1959 年",
                sales: 38
            },
            {
                year: "1960 年",
                sales: 38
            },
            {
                year: "1962 年",
                sales: 38
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
