<template>
  <div>
    <Header/>
    <div class="container">
      <div class="bet--coupon--app d-flex justify-content-between align-items-start">
        <MatchList :addMatchToMyCoupon="addMatchToMyCoupon"/>
        <MyCoupon />
      </div>
    </div>
  </div>
</template>

<script>
import Header from './components/Header.vue'
import MatchList from './components/Match/MatchList.vue'
import MyCoupon from './components/MyCoupon/MyCoupon.vue'

export default {
  name: 'App',
  components: {
    Header,MatchList,MyCoupon
  },
  data(){
    return{
      myCouponList:[]
    }
  },
  provide(){
    return{
        myCouponList: this.myCouponList
    }
  },
  methods:{
    addMatchToMyCoupon(match){
      // kupon listemde aynı maç varsa indexi bul
      var indx = this.myCouponList.findIndex( coupon => coupon.matchId == match.matchId );
      // aynı maçı kuponumdan sil
      if(indx>=0) this.myCouponList.splice(indx, 1);
      this.myCouponList.push({
        id: new Date().getTime(),
        matchId: match.matchId,
        name: match.name,
        result: match.result,
        rate: match.rate,
        time: match.time
      });
    }
  }
}
</script>