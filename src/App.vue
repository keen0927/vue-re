<template>
    <div>
        <BottomSheet />
    </div>
</template>

<script>
import BottomSheet from './components/BottomSheet';
export default {
    name: 'App',
    components: {
        BottomSheet
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