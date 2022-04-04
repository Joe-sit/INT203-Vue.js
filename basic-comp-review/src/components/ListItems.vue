<script setup>
defineEmits(['confirm'])
const props = defineProps({
    items: {
        type: Array,
        require: true
    }
})
</script>
 
<template>
    <div>
        <ul>
            <li v-for="(item, index) in items" :key="index">
                <span class="font-bold">Git Repo:</span>
                {{ item.group }}
                <br />
                <span class="font-bold">Project title:</span>
                {{ item.title }}
            </li>
        </ul>
        <br />
        <div>
            <button class="border" @click="$emit('confirm', 'USER_CONFIRM')">confirm</button>
        </div>
    </div>
</template>
 
<style>
</style>