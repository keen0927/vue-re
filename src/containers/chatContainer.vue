<template>
    <div class="chat-container">
        
        <chatList 
            :todos="todoList"
            message="안녕하세요"
        />
        <chatInput 
            @onSearchTotal="handlerListAdd"
            class="mt-2"
        />        
    </div>
</template>

<script>
import chatInput from '../components/chatInput';
import chatList from '../components/chatList';

    export default {
        name: 'chatContainer',
        components: {
            chatInput,
            chatList,
        },
        data() {
            return {
                todoList: [
                    {text: '안녕하세요1'},
                    {text: '안녕하세요2'},
                    {text: '안녕하세요3'},
                ]
            }
        },
        methods: {
            handlerListAdd() {
                console.log('111');
            }
        },
    }
</script>

<style lang="scss" scoped>
.chat-container {
    width: 360px;
    margin: 0 auto;
}
</style>