<script setup>
    import { ref,computed } from 'vue';
    let count = ref(0);

    const increment = () => count.value++;
    const decremenet = () => count.value--;


    let count2 = ref(0);
    const squaredCount2 =  computed(() => {
        return count2.value * count2.value;
    });
    const increment2 = () => count2.value++;
    const decremenet2 = () => count2.value--;


</script>

<template>
    <div class="Counter1">
    <h1> Count : {{count}} </h1>

    <button v-on:click="increment">Increment</button>
    <button @:click="decremenet">Decrement</button>
    </div>

    <div class="Counter2">
        <h1> Counter 2 : {{count2}}</h1>
        <h1>Squared Counter : {{squaredCount2}} </h1>
        <!-- computed() ensures that squaredCount2 only recalculates when count2 changes.
            This improves performance and efficiency in Vue apps by avoiding unnecessary recomputations.
             -->
        <button v-on:click="increment2">Increment</button>
        <button @:click="decremenet2">Decrement</button>
    </div>
</template>

    <style scoped>

    .Counter1, .Counter2{
        display : flex;
        flex-direction : column;
        align-items : center;
        border : 2px solid black;
        padding : 20px;
        margin-left : 25%;
        margin-right : 25%;
        margin-top : 10px;
        margin-bottom : 10px;
    }


    </style>