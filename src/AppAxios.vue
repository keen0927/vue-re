<template>
    <div>
        <button type="button" @click="fetchContacts">조회</button>
        <testSlot :header="A.header" :message="A.message">
            <div>
                TEST
            </div>
        </testSlot>

        <testSlot :header="B.header" :message="B.message">
            <div>
                <ul>
                    <li>가나다라마바사</li>
                    <li>가나다라마바사</li>
                    <li>가나다라마바사</li>
                </ul>
            </div>
        </testSlot>

        <Layout>
            <h1 slot="header">헤더 영역</h1>
            <div slot="content">
                컨텐츠 슬롯
            </div>
        </Layout>

        <button type="button" @click="changeMenu('Home')">HOME</button>
        <button type="button" @click="changeMenu('About')">About</button>

        <keep-alive include="Home, About">
            <component :is="currentView"></component>
        </keep-alive>
        
    </div>
</template>

<script>
import axios from 'axios';
import testSlot from './components/slotTest';
import Layout from './components/NamedSlot';
import Home from './components/Home';
import About from './components/About';

    export default {
        name: "App",
        components: {
            testSlot,
            Layout,
            Home,
            About
        },
        data() {
            return {
                no: 0,
                name: '',
                tel: '',
                address: '',
                result: null,
                A: {
                    header: 'A 헤더',
                    message: 'A 메세지'
                },
                B: {
                    header: 'B 헤더',
                    message: 'B 메세지'
                },
                currentView: 'Home'
            }
        },
        methods: {
            changeMenu(view) {
                this.currentView = view;
            },
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