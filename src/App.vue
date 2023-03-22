<script setup>
import {ref} from 'vue'
import TheHeader from './components/TheHeader.vue';
import HoodieCard from './components/HoodieCard.vue'

import {HOODIES} from './assets/js/hoodies'

// console.log(HOODIES)
const localHoodies = ref(HOODIES)

</script>

<template>

  <TheHeader />
  <div class="container mx-auto mt-4  w-2/3 bg-card-background rounded py-2">
        
        <div id="filters" class="px-4 mt-4 flex space-x-2">
            <span
                class="inline-block whitespace-nowrap rounded-[0.27rem] cursor-pointer bg-tertiary-contrast px-[0.65em] pt-[0.35em] pb-[0.30em] text-center align-baseline text-[0.75em] leading-none text-card-background-light">
                Lacoste
            </span>
            <span
                class="inline-block whitespace-nowrap rounded-[0.27rem] cursor-pointer bg-tertiary-contrast px-[0.65em] pt-[0.35em] pb-[0.30em] text-center align-baseline text-[0.75em] leading-none text-card-background-light">
                Dedicated
            </span>
            <span
                class="inline-block whitespace-nowrap rounded-[0.27rem] cursor-pointer bg-tertiary-contrast px-[0.65em] pt-[0.35em] pb-[0.30em] text-center align-baseline text-[0.75em] leading-none text-card-background-light">
                &#60;100€ 
            </span>
        </div>

        <div id="item-list" class="px-4 ">
            <!-- item card -->
            <HoodieCard 
              v-for="hoodie in localHoodies"
              :key ="hoodie.ref"
              :hoodie="hoodie"
            />

            
        </div>

    </div>



</template>

<style scoped>
</style>
