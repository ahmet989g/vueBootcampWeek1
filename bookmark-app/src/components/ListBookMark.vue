<template>
    <div class="container">
      <div class="bookmark--app--container">
            <BookMarkItem :deleteItem="deleteItem" v-for="bookMarkItem in bookMarkData.bookMarkList" :key="bookMarkItem.id" :item="bookMarkItem" />
      </div>
    </div>
</template>
<script>
    import BookMarkItem from './BookMarkItem.vue'

    export default {
        inject: ["bookMarkData"],
        props: {
            bookMarkList: {
                type: Array,
                required: true
            },
            deleteItem: {
                type: Function
            }
        },
        components: {
            BookMarkItem
        }
    }
</script>