<template>
    <li class="course-item list-item" :class="item.status?'bg-success':'bg-danger'">
        <span>{{ item }}</span>
        <input type="checkbox" v-model="courseItem.status" :checked="courseItem.status" :id="`check_${item.id}`" />
    </li>
</template>
<script>
    export default{
        data(){
            return{
                courseItem:this.item
            }
        },
        props: ["item"]
    }
</script>