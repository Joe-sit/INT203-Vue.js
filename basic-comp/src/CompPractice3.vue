<script setup>
import IconoirCoin from './components/icons/IconoirCoin.vue';
import IconAvatar from './components/icons/IconAvatar.vue'
import ListItems from './components/ListItem.vue';
import { ref } from '@vue/reactivity';
const projects = [
    { section: 1, group: 1, title: 'Bingo' },
    { section: 2, group: 1, title: 'XO' },
    { section: 3, group: 1, title: 'Matching Game' }
]
const currentStatus = ref('NONE')
const updateStatus = (status) => (currentStatus.value = status)

</script>
 
<template>
    <div>
        <icon-avatar />
        <span class="header">INT203' Student's projects</span>
        <div>
            <ListItems :items="projects" @confirm="updateStatus" />
            <p>Current Status : {{ currentStatus }}</p>
        </div>
    </div>
</template>
 
<style>
.header {
    font-weight: bolder;
}
</style>