<script setup>
import LogosBitcoin from './components/icons/IconBitcoin.vue';
import IconAdd from './components/icons/IconAdd.vue';
import ListItems from './components/ListItems.vue';
import { ref } from 'vue';
const projects = [
  { group: 'umaporn-sup/INT203class', section: 1, title: 'Bingo Game' },
  { group: 'student/Sec2_Group1', section: 2, title: 'Flash Card' },
  { group: 'student/Sec3_Group2', section: 3, title: 'Tic Tac Toe' }
]
const chageStatus = (status) => currentStatus.value = status;
const currentStatus = ref('');

</script>
 
<template>
  <div>
    <!-- <LogosBitcoin />
    <h2>Home</h2>
    <p>
      Get more crypto
      <IconAdd />
    </p>-->
    <div class="max-w-sm rounded overflow-hidden shadow-lg">
      <div class="px-6 py-4">
        <div class="font-bold text-xl mb-2">INT203 STUDENT PROJECTS</div>
        <p class="text-gray-700 text-base">
          <ListItems :items="projects" @confirm="chageStatus" />
          current status: {{ currentStatus }}
        </p>
      </div>
    </div>
  </div>
</template>
 
<style>
</style>