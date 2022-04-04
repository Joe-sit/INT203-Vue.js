<script setup>

</script>
 
<template>
    <div>
        <router-link :to="{ name: 'Home' }" id="router-link-home">Home </router-link>
        <router-link :to="{ name: 'MyPortfolio' }" id="router-link">My Portfolio</router-link>
        <div>
            <router-view></router-view>
        </div>
    </div>
</template>
 
<style>
#router-link {
    text-decoration: underline;
    font-weight: bold;
    color: cornflowerblue;
    font-size: 52px;
}
#router-link-home {
    text-decoration: underline;
    font-weight: bold;
    color: rgb(250, 154, 90);
    font-size: 52px;
}
.router-link-active {
    color: blue;
}
</style>