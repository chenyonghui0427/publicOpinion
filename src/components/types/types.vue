<template>
    <div class="type">
        <div
            :class="`type_item  ${currentType==index?'focus':''}`"
            v-for="(item,index) in typeList"
            :key="index"
            @click="selectType(index)"
        >{{item}}</div>
    </div>
</template>

<script>
export default {
    props: {
        typeList: Array
    },
    data() {
        return {
            currentType: 0
        };
    },
    methods: {
        selectType(index) {
            this.currentType = index;
            this.$emit("selectType",{currentType:index})
        }
    }
};
</script>

<!-- Add "scoped" attribute to limit CSS to that component only -->
<style scoped>
.type {
    display: flex;
    justify-content: space-around;
    background: #fff;
}
.type_item {
    width: 22vw;
    height: 50px;
    box-sizing: border-box;
    line-height: 50px;
    font-size: 12px;
    color: #a3a3a3;
    background: #fff;
    border-radius: 4px;
    box-shadow: 0 0 3px #ccc;
    position: relative;
    background: #fff;
    color: #5e7ede;
    padding-left: 10px;
}
.type_item::before {
}
.focus {
    background: #5e7ede;
    color: #fff;
}
.focus::before {
    position: absolute;
    content: "";
    bottom: -8px;
    left: 20px;
    /* top: 10px; */
    height: 10px;
    width: 0;
    height: 0;
    border-width: 0 10px 10px;
    border-style: solid;
    border-color: transparent transparent #5e7ede;
    transform: rotate(180deg);
}
</style>
