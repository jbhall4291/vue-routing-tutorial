<script setup>
import {useRoute} from "vue-router"
import cars from "../data/cars.json"

const route = useRoute();
const currCar = cars.find(car => car.id == route.params.id)
</script>

<template>
    <div v-if="currCar">
        <h1>
            Contact Info
        </h1>
        <p>Contact: {{currCar.contact.dealer}}</p>
        <p>Call: {{currCar.contact.number}}</p>
    </div>
</template>