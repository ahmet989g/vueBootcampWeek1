<template>
  <div class="card">
    <div class="user--action--container">
      <div class="form-group">
        <label>Kursun Adı</label>
        <input type="text" v-model="courseName" @keydown.enter="addCourseData(courseName)" id="courseName" />
      </div>
      <button class="btn-primary" @click="addCourseData(courseName)">Kurs Ekle</button>
    </div>
  </div>
</template>

<script>
export default {
  name: 'AddCourse',
  props: {
      addCourseData:{
        type: Function,
        required: true
      }
  },
  data(){
      return{
          courseName: null
      }
  },
}
</script>