<template>
    <div>
        <!-- <a-input-search 
            placeholder="input search text" 
            @search="onSearch"
            @keyup="onKeyPress"
            enterButton="추가"
            size="large"
        /> -->
        <a-input-search 
            placeholder="input search text" 
            @keyup.enter="onKeyPress"
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
            // onSearch(e) {
            //     console.log(e);
            //     this.$emit('onSearchTotal',e);
            // },
            onKeyPress(e) {
                console.log('엔터');
                let inputValue = e.target.value;
                this.$emit('updateValue', inputValue);
                this.todoInput = '';
            },
            onKeyPress(e) {
                console.log('엔터');
                let inputValue = e.target.value;
                this.$emit('updateValue', inputValue);
                this.todoInput = '';
            }            
        },
    }
</script>

<style lang="scss" scoped>

</style>