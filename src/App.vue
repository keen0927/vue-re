<template>
    <div>
        <!-- <chatContainer /> -->
        <!-- <gugudan />
        <binarySearch /> -->


        <!-- <button name="tab-button" @click="contentShow('.content-area',1)" class="active">1</button>
        <button name="tab-button" @click="contentShow('.content-area',2)">2</button>
        <button name="tab-button" @click="contentShow('.content-area',3)">3</button>
        <button name="tab-button" @click="contentShow('.content-area',4)">4</button> -->

        <button name="tab-button" class="tab-button active" @click="contentShow(1)">1</button>
        <button name="tab-button" class="tab-button" @click="contentShow(2)">2</button>
        <button name="tab-button" class="tab-button" @click="contentShow(3)">3</button>
        <button name="tab-button" class="tab-button" @click="contentShow(4)">4</button>


        <div class="content-area" v-show="isContentArea[0]">1</div>
        <div class="content-area" v-show="isContentArea[1]">2</div>
        <div class="content-area" v-show="isContentArea[2]">3</div>
        <div class="content-area" v-show="isContentArea[3]">4</div>
    </div>
</template>

<script>


import chatContainer from './containers/chatContainer';
// import gugudan from './containers/gugudan';
// import binarySearch from './pages/algorithms/BinarrySearch';

    export default {
        name: 'App',
        data() {
            return {
                isContentArea: [
                    true, false, false, false
                ]
            }
        },
        components: {
            chatContainer,
            // gugudan,
            // binarySearch
        },
        methods: {
            contentShow(index) {
                var isContentAreaControl = [false, false, false, false];
                isContentAreaControl[index-1] = true;
                this.isContentArea = isContentAreaControl;
                var button = document.querySelectorAll('.tab-button');
                var buttonActiveElement = document.querySelector('button.active');

                document.querySelectorAll('.tab-button').forEach(function(val){
                    buttonActiveElement.classList.remove('active');
                    // document.querySelectorAll('.tab-button')[0].classList.add('active');
                    button[index-1].classList.add('active');
                });
                
            }
            // conten(element, index) {
            //     va elementName = '.content-area',
            //        = document.querySelectorAll(elementName),
            //        = document.querySelector('button'),
            //         buttonActiveElement = document.querySelector('button.active'),
            //         indexCalculate = index-1;

            //     if (targetElements[indexCalculate].offsetWidth > 0 || targetElements[indexCalculate].offsetheight > 0) {
            //         return null;
            //     } else {
                    
            //     }
            //     // if (!targetElements[indexCalculate].offsetWidth > 0 || targetElements[indexCalculate].offsetheight > 0) {
            //     //     console.log('11');
            //     //     // targetElements.forEach(function(val){
                        
            //     //     // });
            //     //     // targetElements[indexCalculate].style.display = 'block';
            //     //     // buttonActiveElement.classList.remove('active');
            //     //     // button[indexCalculate].classList.add('active');
            //     // } else {
            //     //     console.log('else');
            //     // }
            // }
        },
        
    }
</script>

<style lang="scss" scoped>
.content-area {
    display: flex;
}
.content-area.hide {
    display: none;
}
button.active {
    background: red;
}
</style>