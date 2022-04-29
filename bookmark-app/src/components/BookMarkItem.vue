<template>
    <div class="bookmark-item">
        <div class="header">
            <h3>{{bookMarkItem.name}}</h3>
            <button class="btn-sm btn-danger" @click="deleteItem(item)">Kaydı Sil</button>
        </div>
        <p class="mt-20 mb-20">{{bookMarkItem.description}}</p>
        <a :href="bookMarkItem.url" class="btn btn-primary btn-sm">Göster</a>
    </div>
</template>
<script>
    export default{
        data(){
            return{
                bookMarkItem:this.item
            }
        },
        props:{
            item:{type:Array},
            deleteItem:{type:Function}
        }
    }
</script>