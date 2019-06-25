<template>
    <div>
        <a-input-search 
            placeholder="input search text" 
            @search="onSearch"
            enterButton="추가"
            size="large"
        />
    </div>
</template>

<script>

    export default {
        name: 'chatInput',
        methods: {
            onSearch() {
                this.$emit('onSearchTotal');
            }
        },
    }
</script>

<style lang="scss" scoped>

</style>