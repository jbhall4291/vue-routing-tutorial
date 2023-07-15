<script setup>
import { useRoute, useRouter, RouterView } from "vue-router"
import cars from "../data/cars.json"

const route = useRoute();
const router = useRouter();

const currCarId = route.params.id;

const currCar = cars.find(car => car.id == currCarId)

</script>



<template>
    <div v-if="currCar">
        <h1>Car View</h1>
        <p>Name: {{ currCar.name }}</p>
        <p>Year: {{ currCar.year }}</p>
        <p>Price: £{{ currCar.price }}</p>
        <button @click="router.push(`${currCarId}/contact`)">Click for contact</button>
        <RouterView />
    </div>
    <div v-else>
        <h1>car not found!</h1>
    </div>
</template>