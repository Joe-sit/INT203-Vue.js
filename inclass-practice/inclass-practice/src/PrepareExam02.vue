<script setup>
// const account = {
//     id: 123,
//     name: 'James',
//     age: 20,
//     role: 'Admin'
// }
const courses = [
    {
        courseID: 'INT201',
        courseName: 'Client I',
        credit: 2
    },
    {
        courseID: 'INT202',
        courseName: 'Client II',
        credit: 2
    },
    {
        courseID: 'INT209',
        courseName: 'DevOps',
        credit: 1
    },
]
</script>
 
<template>
    <ul>
        <li v-for="(course, propKey) in courses" :key="course.courseID">
            {{ propKey }}--
            {{ course.courseID }}
            {{ course.courseName }}
            credit: {{ course.credit }}
        </li>
    </ul>
    <!-- <ul class="list-disc">
        <li
            v-for="(value, propKey, index) in account"
            :key="account.id"
        >{{ index }}--{{ propKey }}: {{ value }}</li>
    </ul>-->
</template>
 
<style>
</style>