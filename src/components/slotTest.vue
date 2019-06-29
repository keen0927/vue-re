<template>
    <div>
        <div>{{header}}</div>
        <slot></slot>
        <div>{{message}}</div>
    </div>
</template>

<script>
    export default {
        name: 'slotTest',
        props: [
            "header",
            "message"
        ]
    }
</script>

<style lang="scss" scoped>

</style>