<template>
    <div>
ddd
<button type="button" @click="fetchContacts">조회</button>
    </div>
</template>

<script>
import axios from 'axios';

    export default {
        name: "App",
        data() {
            return {
                no: 0,
                name: '',
                tel: '',
                address: '',
                result: null
            }
        },
        methods: {
            fetchContacts() {
                axios({
                    method: 'GET',
                    url: 'http://sample.bmaster.kro.kr/contacts',
                    params: { 
                        pageno: 2,
                        pagesize: 5
                    }
                })
                .then((res) => {
                    console.log(res)
                })
                .catch((err) => {
                    console.error(err)
                })
            },
            addontact() {

            },
            fetchContactOne() {

            }
        },
    }
</script>

<style lang="scss" scoped>

</style>