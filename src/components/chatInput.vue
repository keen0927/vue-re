<template>
    <div>
        <a-input-search 
            placeholder="input search text" 
            @search="onSearch"
            @keyup="onKeyPress"
            enterButton="추가"
            size="large"
        />
    </div>
</template>

<script>

    export default {
        name: 'chatInput',
        props: [
            "todoInput"
        ],
        methods: {
            onSearch(e) {
                this.$emit('onSearchTotal',e);
            },
            onKeyPress(e) {
                // this.$emit()
                let thisValue = e.target.value;
                console.log(thisValue);
                this.$emit('updateValue',thisValue)
            }
        },
    }
</script>

<style lang="scss" scoped>

</style>