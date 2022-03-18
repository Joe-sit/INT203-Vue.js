<script setup>
import { ref } from '@vue/reactivity';
import BaseButtonColor from './components/BaseButtonColor.vue';
const buttonText = ref('Default');
const buttonColor = ref("#000000");
</script>
 
<template>
    <div>
        <div>
            yourText: {{ buttonText }}
            <input
                type="text"
                v-model="buttonText"
                placeholder="insert button name here"
            />
        </div>

        <div>
            Your Color:{{ buttonColor }}
            <input type="color" v-model="buttonColor" />
        </div>
        <BaseButtonColor :yourText="buttonText" :yourColor="buttonColor" />
    </div>
</template>
 
<style>
</style>