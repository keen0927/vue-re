

<template>
  <div id="app" @contextmenu.prevent="ctxStop">
    <p>
      <input 
        id="textInput"
        type="text"
        :style="style1"
        @keyup.enter="deposit"
        @mouseover.stop="overEvent"
        @mouseout.stop="outEvent"
        v-model="amount">
    </p>
    <p v-show="isValidate === true">올바른 수를 입력하세요</p>
    <button id="deposit" @click="deposit()">예금</button>
    <button id="withdraw" @click="withdraw()">인출</button>
    <h3>계좌잔고 : {{balance}}</h3>
    <button id="btn1" :style="[myColor, myLayout]">스타일 버튼</button>
    <button :class="{btnPrimary: bindStyle1,btnSecondary: bindStyle2}">테스트</button>
    <ul>
      <li><input type="checkbox" v-model="bindStyle1">check 1</li>
      <li><input type="checkbox" v-model="bindStyle2">check 2</li>
    </ul>
    점수 : <input type="text" class="score" v-model.number="score" :class="info">
    <p class="warning-image" v-show="info.warning">ㅋ</p>
  </div>
</template>

<script>



export default {
  name: 'App',
  data: function(){
    return {
      score: 0,
      amount: 0,
      balance: 0,
      isValidate: false,
      style1: {
        border: "2px solid olive",
        borderRadius: "4px",
        backgroundColor: "aqua"
      },
      myColor: {
        color: "blue"
      },
      myLayout: {
        padding: "20px"
      },
      bindStyle1: false,
      bindStyle2: false
    }
  },
  methods: {
    overEvent() {
      this.style1.backgroundColor = "gray"
    },
    outEvent() {
      this.style1.backgroundColor = "aqua"
    },
    // deposit() {
    //   this.balance += parseInt(this.amount);
    //   this.amount = 0;
    // },
    // withdraw() {
    //   this.balance -= parseInt(this.amount);
    //   this.amount = 0;
    // }    
    deposit(e) {
      var amt = parseInt(this.amount);
      if (amt <= 0) {
        this.isValidate = true
        this.amount = 0;
        document.getElementById('#textInput');
      } else {
        this.balance += amt;
        this.isValidate = false;
      }
    },
    withdraw() {
      var amt = parseInt(this.amount);
      if (amt <= 0) {
        this.isValidate = true;
        this.amount = 0;
        document.getElementById('#textInput');
      } else {
        this.balance -= amt;
        this.isValidate = false;
      }
    },
    // ctxStop() {
    //   // e.preventDefault();
    //   console.log('111');
    // }
    ctxStop: function(e) {
      e.preventDefault();
    }
    
  },
  computed: {
    info() {
      if (this.score >=1 && this.score <= 100) {
        return { warning: false}
      } else {
        return { warning: true}
      }
    }
  },
}
</script>

<style lang="scss">
  .btnPrimary {
    color: blue;
    border: 1px solid blue;
  }
  .btnSecondary {
    color: gray;
    border: 1px solid gray;
  }
  .score {
    border: 1px solid #000;
  }
  .warning {
    background-color: orange;
    color: purple;
  }
  .warning-image {
    width: 18px;
    height: 18px;
    top: 5px;
    position: relative
  }
</style>
