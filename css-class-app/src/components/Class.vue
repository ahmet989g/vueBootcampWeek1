<template>
  <div>
    <header>CSS Class App</header>
    <div class="container css--class--app">
      <div class="card text-center">
        <ul class="css--palette text-center">
          <li v-for="color in colors" :key="color" :class="color" @click="changeBoxColor(color)"></li>
        </ul>
        <div class="result-box" :class="selectedClass"></div>
      </div>
    </div>
  </div>
</template>
<style>
  .yesil{background-color: #18bf71!important;}
  .sari{background-color: #ffff00!important;}
  .lacivert{background-color: #1565c0!important;}
  .siyah{background-color: #000000!important;}
  .mor{background-color: #6a1b9a!important;}
</style>
<script>
export default {
  data(){
        return{
            colors: ['yesil','sari','lacivert', 'siyah', 'mor'],
            selectedClass: 'yesil'
        }
    },
    methods: {
      changeBoxColor(color){
        this.selectedClass = color;
      }
    }
}
</script>
