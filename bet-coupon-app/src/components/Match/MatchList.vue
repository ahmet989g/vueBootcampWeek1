<template>
    <!-- Mac Listesi-->
    <div class="card competition-list mr-10">
        <div class="card--header">
        <h4>Yakın Zamanda Başlayacak Müsabakalar</h4>
        </div>
        <div class="card--body">
            <MatchItem :addMatchToMyCoupon="addMatchToMyCoupon" v-for="match in matchList" :key="match.id" :item="match"/>
        </div>
    </div>
</template>
<script>
import MatchItem from './MatchItem.vue'

export default{
  data(){
    return{
      matchList:[
        {id:1, name:"Fenerbahçe x Galatasaray",rates:[{id:1,rate:1.55,result:1},{id:2,rate:2.55,result:0},{id:3,rate:1.65,result:2}],time:"19:00"},
        {id:2, name:"Beşiktaş x Başakşehir FK",rates:[{id:1,rate:1.45,result:1},{id:2,rate:3.55,result:0},{id:3,rate:1.85,result:2}],time:"21:00"}
      ]
    }
  },
  props: {
      addMatchToMyCoupon:{type: Function}
  },
  components: {
    MatchItem
  },
  provide(){
    return{
      matchList: this.matchList,
    }
  },
}
</script>
