<template>
    <div>
        <SearchComponent @gogosing="handlerSearchAPI"/>
        <ContactlistComponent />
    </div>
</template>

<script>
    import SearchComponent from '../components/SearchComponent';
    import ContactlistComponent from '../components/ContactlistComponent';
    export default {
        name: 'SearchContact',
        components: {
            SearchComponent,
            ContactlistComponent
        },
        methods: {
            handlerSearchAPI(eventValue) {
                console.log(eventValue)
            }
        },
    
    }
</script>

<style lang="scss" scoped>

</style>