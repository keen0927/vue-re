<template>
    <div>
        <h1>Event 버스 A</h1>
        <button 
            type="button"
            @click="clickEvent"
        >버튼 A</button>
        <div>{{currentTime}}</div>
        <button type="button" @click="rxjsFunction">RXJS 테스트</button>
    </div>
</template>

<script>
    import { range } from 'rxjs';
    import { map, filter } from 'rxjs/operators';

    export default {
        name: "EventBusChildA",
        data() {
            return {
                currentTime: ''
            }
        },
        methods: {
            clickEvent() {
                let d = new Date();
                let t = d.toLocaleTimeString();
                eventBus.$emit('click1',t)
                
            },
            rxjsFunction() {
                range(1,20).pipe(
                    filter( x => x % 2 === 1),
                    map(x => x + x)
                ).subscribe(x => console.log(x));
            }
        },
        created () {
            console.log('created');
            function foodReport(name,age,...favoriteFoods) {
                console.log(name);
                console.log(age);
                console.log(favoriteFoods);
            }
            foodReport('keen','37','피자','바베큐');
            
            let url = "http://sample.bmaster.kro.kr/contacts_long/search/ja";
            
            fetch(url)
                .then((response) => response.json())
                .then((json) => console.log(json))
                .catch((error) => console.log(error.message))
        }
    }
</script>

<style lang="scss" scoped>

</style>