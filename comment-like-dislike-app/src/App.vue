<template>
  <Header/>
  <CommentList/>
</template>

<script>
import Header from './components/Header.vue'
import CommentList from './components/CommentList.vue'

export default {
  name: 'App',
  components: {
    Header,CommentList
  },
  data(){
    return{
      commentList:[
        { id:1, likeCount:20, dislikeCount:5, text:"Lorem ipsum dolor sit amet, consectetur adipisicing elit. Sint deserunt, tempore accusamus iusto nobis dolore ratione itaque perferendis delectus? Nostrum corporis, quod voluptates quis consequuntur eveniet beatae dolor aperiam ad" },
        { id:2, likeCount:8, dislikeCount:1, text:"Lorem ipsum dolor sit amet, consectetur adipisicing elit. Sint deserunt, tempore accusamus iusto nobis dolore ratione itaque perferendis delectus? Nostrum corporis, quod voluptates quis consequuntur eveniet beatae dolor aperiam ad" },
        { id:3, likeCount:0, dislikeCount:0, text:"Lorem ipsum dolor sit amet, consectetur adipisicing elit. Sint deserunt, tempore accusamus iusto nobis dolore ratione itaque perferendis delectus? Nostrum corporis, quod voluptates quis consequuntur eveniet beatae dolor aperiam ad" },
        { id:4, likeCount:10, dislikeCount:3, text:"Lorem ipsum dolor sit amet, consectetur adipisicing elit. Sint deserunt, tempore accusamus iusto nobis dolore ratione itaque perferendis delectus? Nostrum corporis, quod voluptates quis consequuntur eveniet beatae dolor aperiam ad" }
      ]
    }
  },
  provide(){
    return{
      commentList: this.commentList,
    }
  },
}
</script>