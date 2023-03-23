<script setup>
import {ref} from 'vue'
import TheHeader from './components/TheHeader.vue';
import HoodieCard from './components/HoodieCard.vue'

import {HOODIES} from './assets/js/hoodies'

// console.log(HOODIES)
const localHoodies = ref(HOODIES)
const isModalVisible= ref(false)
const hoodieCart = ref([])

const tailles = ['S','M','L','XL']

const addHoodieToCart = (data)=>{

  // on vérifie si le hoodie est déjà dans le panier ou pas 

  const hoodieIdx = hoodieCart.value.findIndex((hood)=>hood.ref==data.ref)
  const hoodie    = localHoodies.value.find((hood)=>hood.ref==data.ref) 
  const oneCommand = {
        ref:data.ref,
        taille:tailles[data.taille],
        preview: hoodie.picture,
        commandPrice:hoodie.price*data.qty
  }
  

  if(hoodieIdx>-1){ // sinon je met à jour 
    hoodieCart.value[hoodieIdx] = oneCommand
  }else{ //pas déjà dans le panier, push "simple"
    hoodieCart.value.push(oneCommand)
  }

  // une ligne dans le panier: un modèle de hoodie et une quantité
  




  

}


</script>

<template>

  <TheHeader 
        @on-open-modal="isModalVisible=true"
  />
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
        <br />
            {{ hoodieCart }}
        <div id="item-list" class="px-4 ">
            <!-- item card -->
            <HoodieCard 
              v-for="hoodie in localHoodies"
              :key ="hoodie.ref"
              :hoodie="hoodie"
              @on-selected-hoodie="addHoodieToCart"
            />

            
        </div>

    </div>
    <div
        class="fixed inset-0 bg-gray-600 bg-opacity-50 overflow-y-auto h-full w-full"
        :class="isModalVisible?'':'hidden'"
    >
    <!-- modal -->
        <div
	        class="relative top-20 mx-auto p-5 border w-2/4 shadow-lg rounded-md bg-white"
        >
        <div class="mt-0 text-center">
            <div
                class="mx-auto flex items-center justify-center"
            >
            <h3 class="text-lg leading-6 font-medium text-gray-900">VOTRE PANIER: / TOTAL EN EUROS / </h3>
            </div>
            
            <div class="mt-2 px-7 py-3">
                <p class="text-sm text-gray-500"> 
                    <!-- liste panier -->
                    <div
                        class="p-5 border shadow-lg rounded-md bg-white text-left h-20 flex justify-start space-x-8 mb-2"
                    >
                        <img
                            class="rounded-md object-cover h-auto "
                            src="https://cdn.shopify.com/s/files/1/0550/6996/6414/products/6560_1800x.jpg?v=1645098113"
                            alt="" />
                        <span>Title sweat</span>
                        <span>PRIX</span>  
                    </div>
                    
                </p>
            </div>
            <div class="items-center px-4 py-3">
                <button
                    @click="isModalVisible=false"
                    class="px-4 py-2 bg-tertiary-contrast text-white text-base font-medium rounded-md w-full shadow-sm hover:opacity-90"
                >
                    CONFIRM COMMAND
                </button>
            </div>
        </div>
    </div>




    </div>



</template>

<style scoped>
</style>
