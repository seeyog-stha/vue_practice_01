<script setup>
import { ref , computed} from 'vue';
const values = ref({
    id:1,
    data:[
        1,
        2,
        3
    ]
})
const first = ref("math")
const last = ref("doe")
const hasdata= computed((previous)=>{
    return values.value.data.length>0? "yes":"false"
})
const getseteg=computed({
    // getter 
    get(){
        return first.value+last.value;
    },
    set(newvalue){
        [first.value,last.value]= newvalue.split(" ")

    }
})
getseteg.value="seeyog stha"
const count = ref(0)
const handlecount =computed({
    get(previous){
        if(count.value<3){
            return count.value
        }
        return previous
    },
    set(newvalue){
        count.value=newvalue
    }
})
const handleclick =()=>{
    handleclick.value= count.value++
}
</script>
<template>
    <main>
        
        <p>has data</p>
        <span>{{ hasdata }}</span>
        <br>
        <span>{{ getseteg }}</span>
        <br>
        <span @click="handleclick">{{ handlecount }}</span>
    </main>
</template>