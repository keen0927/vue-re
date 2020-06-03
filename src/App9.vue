<template>
    <div>
        <chatContainer />
        <hr />
        <gugudan />
    </div>
</template>

<script>


import chatContainer from './containers/chatContainer';
import gugudan from './containers/gugudan';

    export default {
        name: 'App',
        components: {
            chatContainer,
            gugudan
        },
    }
</script>

<style lang="scss" scoped>

</style>