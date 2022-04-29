<template>
    <button @click="setAmount(amount)" class="btn-sm">{{amount}}</button>
</template>
<script>
    export default{
        data(){
            return{
                amount:this.item
            }
        },
        props:{
            item:{type:Array},
            setAmount:{type: Function},
        }
    }
</script>