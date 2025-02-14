<script setup>
const msg = "hello world"
const html = "<span>hello form html</span>"
const id = 2
let isdisabled = true // "" is also treated as true
//   incase of multiple attributes
const objectOfAttrs = {
    id: 'container',
    class: 'wrapper',
    style: 'background-color:green'
}
const red = () => {
    console.log("hello")
}
const event= "click"
</script>
<template>
    <p>{{ msg }}</p>
    <p>{{ html }}</p>
    <p v-html="html"></p>
    <p :id="`id-${12}`">elite</p>
    <button :disabled="isdisabled">elite</button>
    <p v-bind="objectOfAttrs">these comp has multiple attributes</p>
    <p>{{ red() }}</p>
    <p v-if="isdisabled"> this is v-if</p>
    <button @click="red">click me</button>
    <button @[event]="red">same click me</button>
    <form @submit.prevent="red"></form>
</template>