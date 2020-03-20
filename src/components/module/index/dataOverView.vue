<template>
    <div>
        <div class="title_top background_white">
            <div class="title">数据概况</div>
            <div class="time_select">
                <span class="time_item hover" v-for="(item,index) in timeList" :key="index">{{item}}</span>
            </div>
        </div>
        <van-swipe indicator-color="white">
            <van-swipe-item>
                <div class="panel background_white">
                    <div class="panel_item">
                        <div class="panel_title">访问人数</div>
                        <div class="panel_data">263</div>
                        <div class="panel_data_day">日:15.23%</div>
                        <div class="panel_data_week">周:45.13%</div>
                        <div class="panel_data_month">月:25.13%</div>
                    </div>
                    <div class="panel_item">
                        <div class="panel_title">访问人数</div>
                        <div class="panel_data">263</div>
                        <div class="panel_data_day">日:15.23%</div>
                        <div class="panel_data_week">周:45.13%</div>
                        <div class="panel_data_month">月:25.13%</div>
                    </div>
                    <div class="panel_item">
                        <div class="panel_title">访问人数</div>
                        <div class="panel_data">263</div>
                        <div class="panel_data_day">日:15.23%</div>
                        <div class="panel_data_week">周:45.13%</div>
                        <div class="panel_data_month">月:25.13%</div>
                    </div>
                    <div class="panel_item">
                        <div class="panel_title">访问人数</div>
                        <div class="panel_data">263</div>
                        <div class="panel_data_day">日:15.23%</div>
                        <div class="panel_data_week">周:45.13%</div>
                        <div class="panel_data_month">月:25.13%</div>
                    </div>
                </div>
            </van-swipe-item>
            <van-swipe-item>
                <div class="panel background_white">
                    <div class="panel_item">
                        <div class="panel_title">访问人数</div>
                        <div class="panel_data">263</div>
                        <div class="panel_data_day">日:15.23%</div>
                        <div class="panel_data_week">周:45.13%</div>
                        <div class="panel_data_month">月:25.13%</div>
                    </div>
                    <div class="panel_item">
                        <div class="panel_title">访问人数</div>
                        <div class="panel_data">263</div>
                        <div class="panel_data_day">日:15.23%</div>
                        <div class="panel_data_week">周:45.13%</div>
                        <div class="panel_data_month">月:25.13%</div>
                    </div>
                    <div class="panel_item">
                        <div class="panel_title">访问人数</div>
                        <div class="panel_data">263</div>
                        <div class="panel_data_day">日:15.23%</div>
                        <div class="panel_data_week">周:45.13%</div>
                        <div class="panel_data_month">月:25.13%</div>
                    </div>
                </div>
            </van-swipe-item>
        </van-swipe>
        <div class=""></div>
        <!-- <LineCharts class="mt" id="id_one" /> -->
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
            timeList: ["今天", "昨日", "7天", "30天"]
        };
    },
    methods: {},
    mounted() {}
};
</script>
<style scoped>
.background_white {
    background: #fff;
}
.mt {
    margin-top: 10px;
}
/* public */
.title_top {
    padding: 10px;
    display: flex;
    justify-content: space-between;
    align-items: center;
}
.title {
    padding-left: 15px;
    position: relative;
    font-size: 20px;
    font-weight: 550;
    /* background: red; */
}
.title::before {
    position: absolute;
    width: 6px;
    top: 4px;
    bottom: 2px;
    left: 0;
    background: #000;
    content: "";
}
.time_select {
    font-size: 14px;
}
.time_item {
    margin-left: 8px;
}
.hover {
    color: #5e7ede;
    border-bottom: 3px #1f47f2 solid;
}
.panel {
    display: flex;
    justify-content: space-around;
}
.panel_item {
    flex: 1;
    margin: 10px 0;
    /* width: 24vw; */
    /* background: red; */
    text-align: center;
}
.panel_item:nth-child(1),
.panel_item:nth-child(2),
.panel_item:nth-child(3){
    border-right: 2px solid #f2f2f2;
}
.panel_title {
    font-size: 14px;
    font-weight: 550;
}

.panel_data {
    font-size: 18px;
    font-weight: 600;
    padding: 10px 0;
}
.panel_data_day {
    color: #eb6974;
    font-size: 12px;
    padding-bottom: 5px;
}
.panel_data_week,
.panel_data_month {
    color: #64c09d;
    font-size: 12px;
    padding-bottom: 5px;
}
</style>
