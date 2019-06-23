<template>
    <div>
        <h1>Event 버스 A</h1>
        <button 
            type="button"
            @click="clickEvent"
        >버튼 A</button>
        <div>{{currentTime}}</div>
    </div>
</template>

<script>
    export default {
        name: "EventBusChildA",
        data() {
            return {
                currentTime: ''
            }
        },
        methods: {
            clickEvent() {
                let d = new Date();
                let t = d.toLocaleTimeString();
                eventBus.$emit('click1',t)
                
            }
        },
    }
</script>

<style lang="scss" scoped>

</style>