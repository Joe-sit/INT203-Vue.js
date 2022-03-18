<script setup>
// Local Registration
import BaseButton from './components/BaseButton.vue'
import IconoirCoin from './components/icons/IconoirCoin.vue'
import BaseButton2 from './components/BaseButton2.vue'
import BaseButton3 from './components/BaseButton3.vue'



console.clear()
const TestMe1 = () => console.log("test me 1");
const TestMe2 = (e) => console.log("test me 2", e);

const TestMe3 = (e) => console.log("test me 3", e);
const TestMe4 = (e) => console.log("test me 4", e);
const TestMe5 = (e, n) => console.log("test me 5", e, n);
const TestMe6 = (e, n) => console.log("test me 6", e, n);

const updateMe1 = (e) => console.log("update me 1", e);
const updateMe2 = (e) => console.log("update me 2", e);
const updateMe3 = (e) => console.log("update me 3", e[0], e[1], e[2]);
const updateMe4 = (e) => console.log("update me 4", e);
const updateMe5 = (e) => console.log("update me 5", e.result);
const updateMe6 = (e, x) => console.log("update me 6", e, x);

</script>
 
<template>
  <div>
    <IconoirCoin />
    <div>
      <button @click="TestMe1">Test Me1</button>
      <button @click="TestMe2">Test Me2</button>

      <button @click="TestMe3()">Test Me3</button>
      <button @click="TestMe4($event)">Test Me4</button>
      <button @click="TestMe5($event, 999)">Test Me5</button>
      <button @click="TestMe6(999, $event)">Test Me6</button>
    </div>

    <div>
      <BaseButton button-name="Click Me1" @clickMe="TestMe1" />
      <BaseButton button-name="Click Me2" @clickMe="TestMe2" />
      <BaseButton button-name="Click Me3" @clickMe="TestMe3()" />
      <BaseButton button-name="Click Me4" @clickMe="TestMe4($event)" />
      <BaseButton button-name="Click Me5" @clickMe="TestMe5($event, 999)" />
      <BaseButton button-name="Click Me6" @clickMe="TestMe6(999, $event)" />
    </div>

    <div>
      <BaseButton2 button-name="Like Me1" @likeMe="TestMe1" />
      <BaseButton2 button-name="Like Me2" @likeMe="TestMe2" />
      <BaseButton2 button-name="Like Me3" @likeMe="TestMe3()" />
      <BaseButton2 button-name="Like Me4" @likeMe="TestMe4($event)" />
      <BaseButton2 button-name="Like Me5" @likeMe="TestMe5($event, 999)" />
      <BaseButton2 button-name="Like Me6" @likeMe="TestMe6(999, $event)" />
    </div>
    <div>
      <BaseButton3 button-name="Update Me1" @updateMe="updateMe1" />
      <BaseButton3 button-name="Update Me2" @updateMe="updateMe2($event)" />
      <BaseButton3 button-name="Update Me3" @updateMe="updateMe3($event)" />
      <BaseButton3 button-name="Update Me4" @updateMe="updateMe4($event)" />
      <BaseButton3 button-name="Update Me5" @updateMe="updateMe5($event)" />
      <BaseButton3 button-name="Update Me6" @updateMe="updateMe6($event, 'DONE')" />
    </div>
  </div>
</template>
 
<style scoped>
</style>