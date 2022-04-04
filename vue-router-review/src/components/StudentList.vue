<script setup>
import { ref } from 'vue'
const students = ref([
    { studentId: 632000121, studentName: 'JOE' },
    { studentId: 632000134, studentName: 'MAMA' },
    { studentId: 632000555, studentName: 'LOL' }
])
</script>
<template>
    <div>
        <ul>
            <li v-for="student in students" :key="student.id">
                Student Name:
                <router-link
                    id="router-link-student"
                    :to="{
                        name: 'StudentItem',
                        params: { studentId: student.studentId }
                    }"
                >{{ student.studentName }}</router-link>
            </li>
        </ul>
    </div>
</template>
<style scoped>
#router-link-student {
    text-decoration: underline;
    color: cornflowerblue;
}
</style>