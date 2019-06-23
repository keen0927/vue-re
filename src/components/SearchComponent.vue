
<template>
    <div>
        이름 : <input 
                type="text"
                v-model.trim="name"
                :placeholder="placeholder"
                @kepup.enter="keyupEvent"
                />
    </div>
</template>

<script>
    export default {
        name: 'SearchComponent',
        methods: {
            handlerEnter(e) {
                this.$emit('gogosing', e.target.value)
            }
        },
    }
</script>

<style lang="scss" scoped>

</style>