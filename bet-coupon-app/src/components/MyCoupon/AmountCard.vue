<template>
    <div class="card card-light multiply--container mt-20">
        <h4 class="text-center mb-10">Mislini Seç</h4>
        <div class="multiply--buttons mb-10 d-flex justify-content-center align-items-center">
            <AmountItem v-for="amount in amountList" :key="amount" :item="amount" :setAmount="setAmount" />
        </div>
        <div class="coupon--total--container mt-20">
            <div class="d-flex justify-content-between align-items-center font-weight-bold">
                <span>Toplam Oran</span>
                <span class="text-info">{{calculateTotalRate}}</span>
            </div>
            <div class="d-flex justify-content-between align-items-center mt-5">
                <span>Kupon Tutarı</span>
                <span class="font-weight-bold">{{calculateCouponAmount}} TL</span>
            </div>
            <div class="d-flex justify-content-between align-items-center mt-5">
                <span>Tahmini Kazanç</span>
                <span class="font-weight-bold text-info">{{calculateTotalAmount}} TL</span>
            </div>
        </div>
    </div>
</template>
<script>
    import AmountItem from './AmountItem.vue'
    export default{
        inject: ["myCouponList"],
        data(){
            return{
                amountList: [5,10,20,30,50,100,200,500,1000,1500,2500],
                totalRate:0,
                couponAmount:1,
                resultAmount:0,
                myCouponList:this.myCouponList
            }
        },
        components: {
            AmountItem
        },
        methods:{
            setAmount(amount){
                this.couponAmount = amount;
            }
        },
        computed:{
            calculateTotalRate(){
                if(this.myCouponList.length>0){
                    var totalRate = Math.round(this.myCouponList.map((x) => x.rate).reduce((a, b) => a * b) * 100) / 100;
                    return totalRate.toFixed(2);
                }
                return this.totalRate;
            },
            calculateTotalAmount(){
                var totalAmount = this.calculateTotalRate * this.couponAmount;
                return totalAmount.toFixed(2)
            },
            calculateCouponAmount(){
                return this.couponAmount.toFixed(2);
            }
        }
    }
</script>