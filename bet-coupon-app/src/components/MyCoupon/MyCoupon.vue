<template>
    <!-- Kuponum -->
    <div class="coupon--total--container">
        <div class="card my-coupon">
            <div class="card--header">
                <h4>Kuponum</h4>
            </div>
            <div class="card--body">
                <div v-if="myCouponList.length>0">
                    <CouponItem v-for="coupon in myCouponList" :key="coupon.id" :item="coupon" />
                </div>
                <p v-else>Kuponunuz Boş!</p>
            </div>
        </div>
        <AmountCard v-if="myCouponList.length>0"/>
    </div>
</template>
<script>
    import CouponItem from './CouponItem.vue'
    import AmountCard from './AmountCard.vue'
    export default{
        components: {
            CouponItem,AmountCard
        },
        inject: ["myCouponList"],
    }
</script>