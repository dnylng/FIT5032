<script setup>
import { ref, defineProps, reactive } from 'vue';

const props = defineProps({
    msg: {
        type: String,
        required: true,
    }
})

const name = ref('fit5032'); //normally you keep it empty, but here we set a default value
const contact = reactive({
    email: 'fit5032@example.com',
    mobile: '123-456-7890'
})

const isVisible = ref(true); // or false to hide the element

function toggleVisibility() {
    isVisible.value = !isVisible.value;
}

const users = reactive([
    { name: 'Alice', age: 25 },
    { name: 'Bob', age: 30 },
    { name: 'Charlie', age: 35 }
]);

const URL = ref('https://www.monash.edu');

function clickhandler() {
    alert('Button clicked!');
}

const numbers = ref([1, 2, 3, 4, 5]);
const doubledNumbers = numbers.value.map(num => num * 2);
const evenNumbers = numbers.value.filter(num => num % 2 === 0);

</script>

<template>
    <div class="fit5032-msg">
        <h1>FIT5032 - Web Application Development</h1>
        <h1 class="blue">{{ msg }}</h1>
        <p>Welcome to FIT5032!</p>
    </div>

    <input v-model="name"/>
    <p>Your name is: {{ name }}</p>

    <p>{{ contact }}</p>

    <button @click="toggleVisibility">Toggle Visibility</button>
    <p v-if="isVisible">This is visible</p>

        <ul>
            <li v-for="(user, key) in users" :key="key">
                {{ key }}: {{ user }}
            </li>
        </ul>

        <a v-bind:href="URL">Monash University</a>

        <button v-on:click="clickhandler">Click Me</button>
        <p>Numbers: {{ numbers }}</p>
        <p>Doubled Numbers: {{ doubledNumbers }}</p>
        <p>Even Numbers: {{ evenNumbers }}</p>
</template>