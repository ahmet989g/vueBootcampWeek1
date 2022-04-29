<template>
    <div class="rate-item">
        <button class="btn-sm" @click="addMatchToMyCoupon(matchData)">{{matchRates.rate}}</button>
    </div>
</template>
<script>
    export default{
        data(){
            return{
                matchRates:this.item,
                matchData:{
                    matchId: this.match.id,
                    name: this.match.name,
                    result: this.item.result,
                    rate: this.item.rate,
                    time: this.match.time
                }
            }
        },
        props:{
            item:{type:Array},
            match:{type:Array},
            addMatchToMyCoupon:{type: Function}
        }
    }
</script>