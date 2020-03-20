<template>
    <div class="title_top">
        <div class="title">趋势分析</div>
        <div class="time_select">
            <span
                :class="`time_item ${currentTime==index?'hover':''}`"
                v-for="(item,index) in timeList"
                :key="index"
                @click="selectTime(index)"
            >{{item}}</span>
        </div>
    </div>
</template>

<script>
export default {
    props: {
        timeList: Array
    },
    data() {
        return {
            currentTime: 0
        };
    },
    methods: {
        selectTime(index) {
            this.currentTime = index;
            this.$emit("selectTime", { currentType: index });
        }
    }
};
</script>

<!-- Add "scoped" attribute to limit CSS to that component only -->
<style scoped>
/* public */
.title_top {
    padding: 10px;
    display: flex;
    justify-content: space-between;
    align-items: center;
    background: #fff;
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
</style>
