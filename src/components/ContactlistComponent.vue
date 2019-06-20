
<template>
    <div>
        <!-- <div v-if="isSearchEmpty">검색결과가 없엉..</div> -->
        <table>
            <thead>
                <tr>
                    <th>번호</th>
                    <th>이름</th>
                    <th>전화번호</th>
                    <th>주소</th>
                </tr>
            </thead>
            <tbody>
                <tr v-for="(contact, index) in contacts" :key="index">
                    <td>{{contact.no}}</td>
                    <td>{{contact.name}}</td>
                    <td>{{contact.tel}}</td>
                    <td>{{contact.address}}</td>
                </tr>
            </tbody>
        </table>
    </div>
</template>

<script>
    export default {
        name: 'ContactlistComponent',
        props: ['contacts']
    }
</script>

<style lang="scss" scoped>

</style>