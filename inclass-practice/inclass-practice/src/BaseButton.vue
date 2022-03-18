<script setup>
defineEmits(['clickMe'])
const prop = defineProps({
    buttonName:{
        type:String,
        //default:'OK'
        require:true
    }
})
</script>
 
<template>
    <button class="button-color" @click="$emit('clickMe,$event')">
        {{buttonName}}
    </button>
</template>
 
<style scoped> 
.button-color{
    background-color: aqua;
}
</style>