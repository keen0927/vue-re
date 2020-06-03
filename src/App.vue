<template>
    <div>
        <BottomSheet />
        컨텐츠
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
body {
    border: 3px solid #000;
}
</style>