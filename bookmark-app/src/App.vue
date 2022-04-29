<template>
  <div>
    <Header/>
    <ListBookMark :deleteItem="deleteItem" />
  </div>
</template>

<script>
  import Header from './components/Header.vue'
  import ListBookMark from './components/ListBookMark.vue'

  export default {
    name: 'App',
    components: {
      Header,ListBookMark
    },
    data(){
      return{
        bookMarkData:{
          bookMarkList:[
            { id:1, name:"Bookmark 1", description:"Açıklama", url:"https://google.com.tr/"},
            { id:2, name:"Bookmark 2", description:"Açıklama", url:"https://google.com.tr/"},
            { id:3, name:"Bookmark 3", description:"Açıklama", url:"https://google.com.tr/"},
            { id:4, name:"Bookmark 4", description:"Açıklama", url:"https://google.com.tr/"},
            { id:5, name:"Bookmark 5", description:"Açıklama", url:"https://google.com.tr/"}
          ]
        }
      }
    },
    provide(){
      return{
        bookMarkData: this.bookMarkData,
        deleteItem: this.deleteItem
      }
    },
    methods : {
      deleteItem(bookMarkItem){
        this.bookMarkData.bookMarkList = this.bookMarkData.bookMarkList.filter((b) => b != bookMarkItem)
      }
    }
  }
</script>