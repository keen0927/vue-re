<template>
    <div>
        <!-- <ul>
            <li 
                v-for="(todo, index) in todos" 
                :key="index">
                {{ todo.text }}
                <a-button 
                    type="dashed"
                    size="small">
                    삭제
                </a-button>
            </li>
        </ul> -->

        <a-list
            size="small"
            bordered
            :dataSource="todos">
            <a-list-item 
                slot="renderItem"
                slot-scope="todo, index">
                {{todo.text}}
                {{index}}
                <a-button 
                    type="dashed"
                    size="small">
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
        ]
    }
</script>

<style lang="scss" scoped>

</style>