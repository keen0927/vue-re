<template>
    <div>
        <EventBusChildA />
        <EventBusChildB />
    </div>
</template>

<script>
import EventBusChildA from './components/EventBusChildA.vue';
import EventBusChildB from './components/EventBusChildB.vue';

    export default {
        name: 'App',
        components: {
            EventBusChildA,
            EventBusChildB,
        }
    }
</script>

<style lang="scss" scoped>

</style>