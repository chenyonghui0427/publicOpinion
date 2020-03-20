<template>
    <div>
        <Times :timeList="timeList" title="趋势分析" @selectTime="selectTime" />
        <Types :typeList="typeList" @selectType="selectType" />
        <StripCharts id="id_two" />
    </div>
</template>

<script>
const F2 = require("@antv/f2");
import StripCharts from "@/components/charts/strip";
import Types from "@/components/types/types";
import Times from "@/components/times/times";
export default {
    components: {
        StripCharts,
        Types,
        Times
    },
    data() {
        return {
            timeList: ["今天", "昨日", "7天", "30天"],
            typeList: ["访问人数", "新用户数", "打开次数", "访问次数"]
        };
    },
    methods: {
        //获取类型组件点击传递来的参数
        selectType(data) {
            console.log("data==>", data);
        },
        //获取时间组件点击传递来的参数
        selectTime(data) {
            console.log("data==>", data);
        }
    },
    mounted() {}
};
</script>
<style scoped>
</style>
