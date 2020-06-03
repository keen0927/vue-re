<template>
    <div>
        이진 탐색 (바이너리 서치)<br />

        
        {{ binarySearch }}


        
    </div>
</template>

<script>
    export default {
        name: 'BinarySearch',
        data() {
            return {
                arr: [3,5,7,8,5,6,7,8,9,0]
            }
        },
        computed: {
            binarySearch() {
                // let result = 0;
                let arr = this.arr;
                let num = 0;

                let result = arr.filter((element, index, array) => {
                    let arrLen = array.length;
                    console.log(arrLen);
                    // console.log('element :', element),
                    // console.log('index :', index),
                    // console.log('array :', array)

                });


                return result;
            }
        },
    }
</script>

<style lang="scss" scoped>

</style>