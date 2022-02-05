<script setup>

const msg = "Hello,Vue";
const msg2 = "Welcome";
const headStyle = "color:grey; font-size:50px; font-weight:bold;";
const paramStyle = "font-size:20px;";
const paramContent = "It is a long established fact that a reader will be distracted by the readable content of a page when looking at its layout. The point of using Lorem Ipsum is that it has a more-or-less normal distribution of letters, as opposed to using 'Content here, content here', making it look like readable English. ";
const imagePath = "../public/images/kob.png";
const paraStyle = "<i><b>INT203 Web Client II</b></i>";
const hide = false;
const yourName = "Joe";
const depositAmt = 50000;
const interest = 0.1;
const courses = [
    'INT203-Web Client II',
    'INT204-Web Server II',
    'INT209-Devops'

];
const myAccount = {
    accountId: 12345,
    accountName: 'Rapeepat Klamjeen',
    balance: 10000
};

const courses1 = [
    { courseId: 'INT201', courseName: 'Client I', credit: 2 },
    { courseId: 'INT202', courseName: 'Client II', credit: 2 },
    { courseId: 'INT210', courseName: 'Architecture and Deployment', credit: 3 }
];


// < 10000 = no interest
// 10000-49999 =10%
// 50000-99999 =20%
// >=100000 =25%
</script>
 
<template>
    <h1 v-text="msg" :style="headStyle"></h1>
    <h2>{{ msg2 }}</h2>
    <p v-bind:style="paramStyle">{{ paramContent }}</p>
    <img src="./assets/logo.png" />
    <img :src="imagePath" alt="kob" srcset />
    <!--v-html-->
    <p v-html="paraStyle" v-show="hide"></p>
    <!--v-show-->
    <p v-show="yourName">Hello, {{ yourName }}</p>
    <!--Empty String is false so if yourName is empty v-show will be false as well-->
    <p>Deposit Amount = {{ depositAmt }}</p>
    <!--v-if-->
    <p v-if="depositAmt < 10000">Interest : Minimum deposit must be 10000</p>
    <p v-else-if="depositAmt <= 49999">Interest : {{ interest * depositAmt }}</p>
    <p v-else-if="depositAmt <= 99999">Interest : {{ interest * 2 * depositAmt }}</p>
    <p v-else-if="depositAmt >= 100000">Interest :{{ interest * 0.25 * depositAmt }}</p>
    <!--v-for (Array)-->
    <ul class="list-disc">
        <li v-for="(course, index) in courses" :key="index">#{{ index }}-{{ course }}</li>
    </ul>
    <!--v-for (Object)-->
    <ul>
        <!-- <li v-for="(value, propKey) in myAccount" :key="myAccount.accountId"> -->
        <li
            v-for="(value, propKey, index) in myAccount"
            :key="index"
        >{{ index }}- {{ propKey }}: {{ value }}</li>
    </ul>
    <ul>
        <li
            v-for="(course, index) in courses1"
            :key="index"
        >{{ course.courseId }} ,Credit: {{ course.credit }}</li>
    </ul>
    <h1 class="text-3xl font-bold underline">Hello world!</h1>
</template>
 
<style>
</style>