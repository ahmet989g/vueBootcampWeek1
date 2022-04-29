<template>
    <div class="container">
      <div class="comment--like--dislike--app">
        <CommentItem v-for="comment in commentList" :key="comment.id" :item="comment" />
      </div>
    </div>
</template>
<script>
    import CommentItem from './CommentItem.vue'
    
    export default{
        components: {
            CommentItem
        },
        inject: ["commentList"],
    }
</script>