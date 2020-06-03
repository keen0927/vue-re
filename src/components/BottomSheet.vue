<template>
  <div class="bottom-sheet-wrap">
    <div class="dimm-element"></div>
    <div class="bottom-sheet-content" >
      <div class="drag-area" ref="dragArea"></div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'BottomSheet',
  methods: {
    closeBottomSheet(e) {
      // const offsetY = this.offsetTop;
      // console.log(`offsetY : ${offsetY}`);
      // console.log(window.innerHeight);
      // console.log(e.target);
    }
  },
  mounted() {
    const target = this.$refs.dragArea;
    target.addEventListener('touchmove',function(e) {
      console.log(Math.floor(e.targetTouches[0].screenY));
    });
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
}
</style>