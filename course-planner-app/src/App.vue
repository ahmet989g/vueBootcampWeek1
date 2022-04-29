<template>
  <div>
    <Header/>
    <CoursePage :addCourseData="addCourseData" :courseResultText="courseResultText" />
  </div>
</template>

<script>
import Header from './components/Header.vue'
import CoursePage from './components/CoursePage.vue'

export default {
  name: 'App',
  components: {
    Header,
    CoursePage
  },
  data(){
    return{
      courseData:{
        courseList:[
          { id:1, name:"Vue.js", status:true},
          { id:2, name:"React.js", status:false},
          { id:3, name:"Angular.js", status:true},
        ]
      }
    }
  },
  provide(){
    return{
        courseData: this.courseData
    }
  },
  methods:{
    addCourseData(course){
      this.courseData.courseList.push({
          id: new Date().getTime(),
          name: course,
          status: 0
      });
    }
  },
  computed:{
    courseResultText(){
      var complatedLength = this.courseData.courseList.filter((t) => t.status).length;
      var unComplatedLength = this.courseData.courseList.filter((t) => !t.status).length;
      return complatedLength > 0 ? "İzlenmiş "+complatedLength+" adet kursunuz var." : "İzlenmemiş "+unComplatedLength+" adet kursunuz var.";
    }
  }
}
</script>