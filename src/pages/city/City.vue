<template>
    <div>
        <city-header></city-header>
        <city-search></city-search>
        <city-list :hot="hotCities" :cities="cities"></city-list>
        <city-alpabet :alpabet="cities"></city-alpabet>
    </div>
</template>

<script>
import CityHeader from './components/header.vue'
import CitySearch from './components/search.vue'
import CityList from './components/list.vue'
import CityAlpabet from './components/Alphabet.vue'
import axios from 'axios'
export default {
    name: 'City',
    components: {
        CityHeader,
        CitySearch,
        CityList,
        CityAlpabet
    },
    data (){
        return{
            hotCities:[],
            cities:{}
        }
    },
    methods:{
        getCityInfo () {
            axios.get('/api/city.json').then(this.getCitySucc)
        },
        getCitySucc (res) {
            res = res.data
            if(res.ret && res.data){
                this.hotCities = res.data.hotCities
                this.cities = res.data.cities
            }
        }
    },
    mounted(){
        this.getCityInfo();
    }
    
}
</script>

<style lang="stylus" scoped>

</style>
