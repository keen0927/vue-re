<template>
    <div>
        {{age}}
    </div>
</template>

<script>
    export default {
        name: 'childPropsComponent',
        props: {
            age: {
                type: String,
                default: ''
            },
        },
    }
</script>

<style lang="scss" scoped>

</style>