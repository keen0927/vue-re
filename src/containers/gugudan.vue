<template>
    <div>
        {{ x }} 곱하기 {{ y }} 는 {{ z() }} 입니다.
    </div>
</template>

<script>
export default{
    name: "gugudan",
    data() {
        return {
            x: Math.ceil(Math.random() * 9),
            y: Math.ceil(Math.random() * 9),
        }
    },
    methods: {
        z() {
            let calculate = this.x * this.y;
            return calculate;
        }
    },
}
</script>

<style>

</style>




