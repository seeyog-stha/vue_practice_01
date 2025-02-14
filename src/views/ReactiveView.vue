<script setup>
import { ref,nextTick ,reactive} from 'vue';
const values = ref(0);
const obj = {id:ref(0)}
let tests = 0
// limitation of reactive 
// first is not applicable to basic types like string Number
// destructuring causes it to loose its connection 
// cannot replace the entire obj 
const react = reactive({count:0})
const increments = async() => {
    values.value++;
    await nextTick()
    values.value++;
    values.value++;
}
const testincrease = () => {
    tests++;

}
const reactincrease =()=>{
    react.count++
}
const {id} = obj
</script>
<template>
    <main>
        <button @click="increments">inc</button>
        <button @click="testincrease">inc test</button>
        <button @click="reactincrease">inc react</button>
        <p>{{ values }}</p>
        <p>test:{{ tests }}</p>
        <p>test:{{ react.count}}</p>
        <p>test:{{ obj.id}}</p>
        <p>test:{{ obj.id+1}}</p>
        <p>test:{{ id+1}}</p>
    </main>
</template>