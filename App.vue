<template>
<div id="app">
    <link href="https://fonts.googleapis.com/css?family=Arizonia" rel="stylesheet">
    <div :style="{ width: width }" class="qouteCounter">{{qoutes.length}} / 10</div>
    <input name="Write a qoute" v-model= "current" @keyup.enter = "addQoute()" >
    <button @click = "addQoute()">submit</button>
    <ul v-for="(qoute, key) in qoutes" :key="key" class="qoutes" @click="qoutes.splice(key,1)">{{qoute}}</ul>
    click to remove qoute
</div>
</template>

<script>
import first from './components/first'
import second from './components/second'
export default {
    name: 'app',
    data() {
        return {
            qoute: "",
            current: "put a qoute",
            qoutes: []
        }
    },
    components: {},
    methods: {
        addQoute() {
            if (this.qoutes.length < 10) {
                this.qoutes.push(this.current);
            } else {
                alert("gotta delete one");
            }
        }
    },
    computed: {
        width() {
            return ((this.qoutes.length / 10) * 100) + '%';
        }
    }
}
</script>

<style>
.qoutes {
    font-family: Arizonia;
    border-color: black;
    border-radius: 4px;
    border-style: solid;
    font-size: 50px;
}

.qouteCounter {
    background-color: aquamarine;
    width: 100%;
}

#app {
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    display: grid;
    grid-gap: 10px;
}

h3 {
    color: green;
}
</style>
