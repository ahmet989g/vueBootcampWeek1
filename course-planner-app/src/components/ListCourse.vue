<template>
    <div class="card card-light mt-20">
        <h3>Aktif Kurslarım</h3>
        <ul class="list mt-20">
            <CourseItem v-for="courseItem in courseData.courseList" :key="courseItem.id" :item="courseItem" />
        </ul>
    </div>
</template>

<script>
    import CourseItem from './CourseItem.vue'

    export default {
        name: 'CoursePage',
        inject: ["courseData"],
        props: {
            courseList: {
                type: Array,
                required: true
            }
        },
        components: {
            CourseItem
        }
    }
</script>