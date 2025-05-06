<template>
    <main>
        <Form @submit="getDate">
            <FloatLabel variant="in">
            <DatePicker v-model="dates" dateFormat="dd/mm/yy"  id="dates" selectionMode="range" :manualInput="false" showIcon :invalid="!dates"/>
            <label for="dates">Date range</label>
            </FloatLabel>
            <Button label="Submit" icon="pi pi-check" type="submit"/>
        </Form>
    </main>
</template>

<script setup>
import { ref } from 'vue';
import { Form } from '@primevue/forms';
import Button from 'primevue/button';
import DatePicker from 'primevue/datepicker';
import FloatLabel from 'primevue/floatlabel';
import 'primeicons/primeicons.css';

const dates = ref();

// watch(dates, (newVal, oldVal) => {
//     console.log(`Old: ${oldVal} \n new: ${newVal}`)
// });

function getDate() {
    console.log('From: ' + JSON.stringify(dates.value[0]) + ' To: ' + JSON.stringify(dates.value[1]));
    //console.log('To: ' + dates.value[1]);
};
//const getDate = computed((dates) => console.log(dates));




</script>

<style>
@media (min-width: 1024px) {
  .about {
    min-height: 100vh;
    display: flex;
    align-items: center;
  }
}</style>
