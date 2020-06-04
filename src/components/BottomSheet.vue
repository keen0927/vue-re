<template>
  <div class="bottom-sheet-wrap" :class="{opend: isOpen}">
    <div class="dimm-element"></div>
    <div class="bottom-sheet-content">
      <div class="drag-area" ref="dragArea" @touchmove="ddd($event)"></div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'BottomSheet',
  methods: {
    // closeBottomSheet(e) {
      // const offsetY = this.offsetTop;
      // console.log(`offsetY : ${offsetY}`);
      // console.log(window.innerHeight);
      // console.log(e.target);
    // },
    ddd(e) {

      // const {} = e.target
      // const target = this.$refs.dragArea;
      const windowHeight = window.innerHeight;
      const bottomSheetHeight = e.target.parentElement.clientHeight;
      const dragHeight = e.target.clientHeight;
      const bottomSheetHalfHeight = bottomSheetHeight / 2;      
      const getPositionY = Math.floor(e.touches[0].clientY);
      
      if (getPositionY >= windowHeight - bottomSheetHalfHeight) {
        this.isOpen = false;
        console.log('1');
      }
      
    }
  },
  data() {
    return {
      isOpen: true
    }
  },
  mounted() {
    // const target = this.$refs.dragArea;
    // const windowHeight = window.innerHeight;
    // const bottomSheetHeight = target.parentElement.clientHeight;
    // const dragHeight = target.clientHeight;

    // const bottomSheetHalfHeight = bottomSheetHeight / 2;
    // console.log('windowHeight : ', windowHeight);
    // console.log('bottomSheetHeight : ', bottomSheetHeight);
    // console.log('dragHeight : ', dragHeight);

    // target.addEventListener('touchmove',function(e) {
    
    // target.addEventListener('touchmove',function(e) {
    //   const getPositionY = Math.floor(e.touches[0].clientY);
      
    //   if (getPositionY >= windowHeight - bottomSheetHalfHeight) {
    //     this.isOpen = false;
    //     console.log('1');
    //   }
    // });
  }
}
</script>

<style lang="scss" scoped>
.bottom-sheet-wrap {
  position: fixed;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
  z-index: 100;
  width: 100%;
  height: 100%;
  background-color: rgba(0,0,0,0.4);

  .dimm-element {
    position: absolute;
    top: 0;
    right: 0;
    bottom: 0;
    left: 0;
    z-index: 10;
    width: 100%;
    height: 100%;
    border: 1px solid #000;
  }

  .bottom-sheet-content {
    position: fixed;
    bottom: 0;
    left: 0;
    right: 0;
    z-index: 20;
    max-height: 80%;
    min-height: 100px;
    border-radius: 8px 8px 0 0;
    background-color: #fff;

    .drag-area {
      height: 20px;
      border: 1px solid #000;
    }
  }

  &.opend {
    .bottom-sheet-content {
      border: 1px solid #000;
    }
  }
}
</style>