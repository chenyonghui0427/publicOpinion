<template>
    <div id="app">
        <router-view />
    </div>
</template>
<script>
window.onload = function() {
    document.addEventListener("touchstart", function(event) {
        if (event.touches.length > 1) {
            event.preventDefault();
        }
    });
    document.addEventListener("gesturestart", function(event) {
        event.preventDefault();
    });
};
</script>
<style>
#app {
    width: 100vw;
    height: 100vh;
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    color: #fff;
    background: #00065b;
    margin: 0;
    padding: 0;
}
* {
    margin: 0;
    padding: 0;
}
</style>
