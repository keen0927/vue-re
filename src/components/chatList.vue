<template>
    <div>
        <a-list
            size="small"
            bordered
            :dataSource="todos">
            <a-list-item 
                slot="renderItem"
                slot-scope="todo, index"
                :key="index">
                {{todo.text}}
                <a-button 
                    type="dashed"
                    size="small"
                    @click="handlerListDelete(index)">
                    삭제
                </a-button>                
            </a-list-item>
        </a-list>


    </div>
</template>

<script>

    export default {
        name: 'chatInput',
        props: [
            "todos",
            "message"
        ],
        methods: {
            handlerListDelete(index) {
                this.$emit('handlerListDelete',index)
            }
        },

    }
</script>

<style lang="scss" scoped>

</style>