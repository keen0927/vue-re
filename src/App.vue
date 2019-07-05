<template>
    <div>
        <!-- <chatContainer /> -->
        <!-- <gugudan />
        <binarySearch /> -->


        <button name="tab-button" @click="contentShow('.div-wrap',1)" class="active">1</button>
        <button name="tab-button" @click="contentShow('.div-wrap',2)">2</button>
        <button name="tab-button" @click="contentShow('.div-wrap',3)">3</button>
        <button name="tab-button" @click="contentShow('.div-wrap',4)">4</button>


        <div class="div-wrap active" style="display: block">1</div>
        <div class="div-wrap">2</div>
        <div class="div-wrap">3</div>
        <div class="div-wrap">4</div>
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
        
            }
        },
        components: {
            chatContainer,
            // gugudan,
            // binarySearch
        },
        methods: {
            contentShow(element, index) {
                var elementName = element,
                    targetElements = document.querySelectorAll(elementName),
                    // buttonElement = document.querySelector('button.active'),
                    button = document.querySelector('button'),
                    buttonActiveElement = document.querySelector('button.active'),
                    indexCalculate = index-1;

                if (targetElements[indexCalculate].style.display !== "block") {
                    targetElements.forEach(function(val){
                        val.style.display = 'none';
                    });
                    targetElements[indexCalculate].style.display = 'block';
                    buttonActiveElement.classList.remove('active');
                    button[indexCalculate].classList.add('active');
                    // buttonActiveElement[indexCalculate].classList.add('active');
                    // console.log(document.querySelectorAll('name="tab-button"'));
                };
            }
        },
        
    }
</script>

<style lang="scss" scoped>
.div-wrap {
    display: none;
}
button.active {
    background: red;
}
</style>