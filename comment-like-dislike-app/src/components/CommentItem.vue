<template>
    <div class="card mb-10 comment--item">
        <p>{{ comment.text }}</p>
        <div class="action--button--container text-right mt-10">
            <button class="btn-sm btn-success" @click="comment.likeCount++">Beğendim ({{ comment.likeCount }})</button>
            <button class="btn-sm btn-danger" @click="comment.dislikeCount++">Beğenmedim ({{ comment.dislikeCount }})</button>
        </div>
    </div>
</template>
<script>
    export default{
        data(){
            return{
                comment:this.item
            }
        },
        props:{
            item:{type:Array}
        }
    }
</script>