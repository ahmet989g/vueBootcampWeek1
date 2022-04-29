<template>
    <div class="coupon-item">
        <div class="w-100 mb-5 d-flex justify-content-between align-items-center">
            <span class="font-weight-bold">{{coupon.name}}</span>
            <span class="font-weight-bold text-info">{{coupon.rate}}</span>
        </div>
        <div class="w-100 d-flex justify-content-between align-items-center">
            <small class="mt-5">Maç Sonucu : <span class="font-weight-bold">{{coupon.result}}</span></small>
            <small class="text-muted">Saat : {{coupon.time}}</small>
        </div>
    </div>
</template>
<script>
    export default{
        data(){
            return{
                coupon:this.item
            }
        },
        props:{
            item:{type:Array},
        }
    }
</script>