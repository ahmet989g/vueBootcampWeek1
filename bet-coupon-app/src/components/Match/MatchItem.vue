<template>
    <div class="competition-item">
        <div class="info--container">
            <span class="font-weight-bold">{{match.name}}</span>
            <small class="text-muted mt-5"><i>Saat : {{match.time}}</i></small>
        </div>
        <div class="rates">
            <MatchRateItem :addMatchToMyCoupon="addMatchToMyCoupon" v-for="matchRates in match.rates" :key="matchRates.id" :item="matchRates" :match="match" />
        </div>
    </div>
</template>
<script>
    import MatchRateItem from './MatchRateItem.vue'
    export default{
        data(){
            return{
                match:this.item
            }
        },
        components: {
            MatchRateItem
        },
        props:{
            item:{type:Array},
            addMatchToMyCoupon:{type: Function}
        }
    }
</script>