<template>
    <div class="home">
        <div class="content">
            <dataOverView />
            <trendAnalysis class="mt" />
            <visitSource class="mt" />
        </div>
    </div>
</template>

<script>
const F2 = require("@antv/f2");
import dataOverView from "@/components/module/index/dataOverView";
import trendAnalysis from "@/components/module/index/trendAnalysis";
import visitSource from "@/components/module/index/visitSource";
export default {
    components: {
        dataOverView,
        trendAnalysis,
        visitSource
    },
    data() {
        return {};
    },
    methods: {},
    mounted() {}
};
</script>
<style scoped>
.mt {
    margin-top: 10px;
}
</style>
