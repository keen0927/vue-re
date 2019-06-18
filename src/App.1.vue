

<template>
  <div id="app">
 TEA
  </div>
</template>

<script>



export default {
  name: 'App',
  data: function(){
    return {
     
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
