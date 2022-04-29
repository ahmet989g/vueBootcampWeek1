<template>
  <div class="container">
      <div class="course--planner-app--container">
          <AddCourse :addCourseData="addCourseData"/>
          <ListCourse/>
          <ResultBar :courseResultText="courseResultText"/>
      </div>
  </div>
</template>

<script>
    import AddCourse from './AddCourse.vue'
    import ListCourse from './ListCourse.vue'
    import ResultBar from './ResultBar.vue'

    export default {
        name: 'CoursePage',
        inject: ["courseData"],
        components: {
            AddCourse,
            ListCourse,
            ResultBar
        },
        props: {
            addCourseData:{
                type: Function,
                required: true
            },
            courseResultText:{
                type: Function,
            }
        },
        data(){
            return{
                courseName: null
            }
        },
    }
</script>