<template>
    <div class="chat-container">
        
            <chatList 
                @handlerListDelete="handlerListDelete"
                :todos="todoList"
                message="안녕하세요"
            />
            <a-divider orientation="left">내용을 입력 하세요</a-divider>
            <!-- <chatInput 
                @onSearchTotal="handlerListAdd"
                :todoInput="todoInput"
                @updateValue="handlerUpdateValue"
                class="mt-2"
            /> -->
            <chatInput 
                v-model="todoInput"
                @updateValue="handlerAddList"
                class="mt-2"
            />
        
    </div>
</template>

<script>
import chatList from '../components/chatList';
import chatInput from '../components/chatInput';


    export default {
        name: 'chatContainer',
        components: {
            chatList,
            chatInput,
            
        },
        data() {
            return {
                todoInput: '',
                todoList: [
                    {text: '안녕하세요1'},
                    {text: '안녕하세요2'},
                    {text: '안녕하세요3'},
                ]
            }
        },
        methods: {
            handlerListAdd(e) {
                if (e !== "") {
                    this.todoList.push({text: e});
                    this.todoInput = '';
                }
            },
            handlerListDelete(index) {
                this.todoList.splice(index,1)
            },
            handlerUpdateValue(value) {
                console.log('value : ',value);
            },
            handlerAddList(e) {
                this.todoList.push({text: e})
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