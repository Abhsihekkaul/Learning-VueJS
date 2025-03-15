<script setup>
import { ref } from 'vue';

let fruits = ref(["Banana", "Apple", "Mango", "Orange", "Pineapple"]);
let newFruit = ref("");

const books = [
  {
    name: "Atomic Habits",
    author: "James Clear",
    sold: "10M+ copies",
  },
  {
    name: "The 7 Habits of Highly Effective People",
    author: "Stephen R. Covey",
    sold: "40M+ copies",
  },
  {
    name: "The Power of Now",
    author: "Eckhart Tolle",
    sold: "3M+ copies",
  },
  {
    name: "Think and Grow Rich",
    author: "Napoleon Hill",
    sold: "100M+ copies",
  },
  {
    name: "The Subtle Art of Not Giving a F*ck",
    author: "Mark Manson",
    sold: "15M+ copies",
  },
];


let addNewFruit = () => {
    if (newFruit.value.trim() !== "") {
        fruits.value.push(newFruit.value.trim());
        newFruit.value = "";
    }
};
</script>

<template>
    <div class="Fruit-Render">
        <h1>New Fruits Addition</h1>

        <input type="text" v-model="newFruit" placeholder="Enter a new fruit">
        <button @click="addNewFruit">Add Fruit</button>
    </div>

    <div class="Fruit-List">
        <h1>Fruit List</h1>
        <ul>
            <li v-for="(fruit, index) in fruits" :key="index">{{ fruit }}</li>
        </ul>
    </div>

    <div class="books_list">
        <h1>Books List </h1>
        <ul>
            <li class="Book_List_Li"  v-for="(book , index) in books" :key="index">
                <p>The author Name is : {{book.author}}</p>
                <p>The Book Name is : {{book.name}}</p>
                <p>Number of Books sold are : {{book.sold}}</p>
            </li>
            </ul>
        </div>
</template>

<style scoped>
.Book_List_Li {
    border: 1px solid black;
    padding: 10px;
    margin-bottom: 10px;
    border-radius: 5px;
}
</style>