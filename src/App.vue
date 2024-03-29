<script setup>
import {ref} from 'vue';
import {HOODIES} from './assets/js/hoodies'
import HoodieCard from './components/HoodieCard.vue';
import HoodieFilter from './components/HoodieFilter.vue';
import TheHeader from './components/TheHeader.vue';

const hoodies = ref(HOODIES)
const cartModalHidden = ref(true);
const panierTab = ref([]);
const totalPrice = ref(0)

const showCartModal = (truefalse)=>{
    cartModalHidden.value = truefalse;
}

const addHoodieHandler = (data)=>{
    panierTab.value.push(data);
    totalPrice.value += data.price;
    console.log(data, panierTab.value, totalPrice.value);
}

//ameliorer calcul du prix total avec fct js .reduce()
//ajouter badge sur panier lors de l'ajout



</script>

<template>

    <TheHeader
    @onOpenModal="showCartModal(false)"/>
  
    <HoodieFilter/>
  <div class="container mx-auto mt-4  w-2/3 bg-card-background rounded py-2">
        
        
    <div id="item-list" class="px-4 ">
        <!-- item card -->
        <HoodieCard 
            v-for="hoodie in hoodies"
            :key="hoodie.ref"
            :hoodie="hoodie"
            @onAddHoodie="addHoodieHandler"/>
        
    </div>

</div>
<div
        :class="[cartModalHidden?'hidden':'', 'fixed inset-0 bg-gray-600 bg-opacity-50 overflow-y-auto h-full w-full']"
    >
    <!-- modal, active/désactive en enlevant la class 'hidden' -->
        <div
	        class="relative top-20 mx-auto p-5 border w-2/4 shadow-lg rounded-md bg-white"
        >
            <div class="mt-0 text-center">
                <div
                    class="mx-auto flex items-center justify-center"
                >
                <h3 class="text-lg leading-6 font-medium text-gray-900">VOTRE PANIER: {{totalPrice}} € </h3>
                </div>
                
                <div class="mt-2 px-7 py-3">
                    <p class="text-sm text-gray-500"> 
                        <!-- liste panier -->
                        <div v-for="hoodie in panierTab"
                            class="p-5 border shadow-lg rounded-md bg-white text-left h-20 flex justify-start space-x-8 mb-2"
                        >
                            <img
                                class="rounded-md object-cover h-auto "
                                :src="`/src/assets/img/${hoodie.picture}`"
                                alt="" />
                            <span>{{hoodie.ref}} / {{ hoodie.name }} {{ hoodie.size }}</span>
                            <span>{{hoodie.price}} €</span>  
                        </div>
                        
                    </p>
                </div>
                <div class="items-center px-4 py-3">
                    <button
                    @click="showCartModal(true)"
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
