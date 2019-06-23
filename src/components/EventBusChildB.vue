<template>
    <div>
        <h2>Event 버스 B</h2>
        <ul>
            <li v-for="(t, index) in timeList" :key="index">
                {{ t }}
            </li>
        </ul>
    </div>
</template>

<script>
    export default {
        name: "EventBusChildB",
        data() {
            return {
                timeList: []
            }
        },
        created () {
            eventBud.$on('click1',this.child1Click)
        },
        methods: {
            child1Click(time) {
                this.timeList.push(time);
            }
        },
    }
</script>

<style lang="scss" scoped>
h2 {
    margin-top: 30px;
}
</style>