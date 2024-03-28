<script setup>
import {ref} from "vue"

const selectedSize = ref("");
const panierTab = ref([]);
const props = defineProps({
    hoodie:{
        type:Object
    }
})


const handleSizeBtn = (size)=>{
    console.log(size);
    if(selectedSize.value == size){
        selectedSize.value = "";
    } else {
        selectedSize.value = size
    };
}

const addToArray = (newObj)=>{

    panierTab.value.push(newObj);
    console.log(panierTab.value);
}

const addToCart = ()=>{
    const panierObj = {
        price:props.hoodie.price,
        name:props.hoodie.name,
        size: selectedSize.value,
        picture: props.hoodie.picture
    };
    console.log(panierObj);
    addToArray(panierObj);
    
}





</script>

<template>
  <div class="flex w-full border-b-2 border-tertiary-contrast mt-6">
        <div class="flex rounded-lg bg-card-background-light shadow-lg flex-row w-full">
            <img
                class="h-96 w-full rounded-t-lg object-cover md:h-auto md:w-48 md:rounded-none md:rounded-l-lg"
                :src="'./src/assets/img/'+hoodie.picture"
                alt="" />
            <div class="flex flex-col justify-start p-6">
                <h5   class="mb-2 text-2xl font-bold text-neutral-800">
                    {{hoodie.name}}
                    <span  class="inline-block ml-4 bg-button-background  border-button-text rounded-md border-2 border-primary px-6 py-2  text-sm font-bold uppercase leading-normal text-primary ">
                        {{hoodie.price}}€ 
                    </span>
                </h5>

                <p class="mb-4 text-base text-neutral-600">
                    {{hoodie.description}}
                </p>
                <p class="text-xs text-neutral-600 space-x-1">
                    <button
                        v-for="(totalStock) in hoodie.globalStock"
                        :key="totalStock.size"
                        :disabled="totalStock.stock==0"
                        @click="handleSizeBtn(totalStock.size)"
                        type="button"
                        :class="[selectedSize==totalStock.size? 'border-button-text' : 'border-tertiary-contrast','disabled:opacity-50 inline-block rounded border-2  border-opacity-75 px-6 pt-2 pb-2 text-xs font-medium uppercase leading-normal text-info']"
                    >
                        {{totalStock.size}}
                    </button>
                </p>
                <div class="flex flex-row mt-8">
                    <div class="basis-1/4">
                        <button
                            type="button"
                            @click="addToCart"
                            class="inline-block rounded border-2 bg-tertiary-contrast text-card-background-light border-button-text px-6 pt-2 pb-2 text-xs font-medium uppercase leading-normal text-info w-44"
                        >
                            ADD TO CART 
                            <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="ml-2 w-6 h-6 float-right">
                                <path stroke-linecap="round" stroke-linejoin="round" d="M2.25 3h1.386c.51 0 .955.343 1.087.835l.383 1.437M7.5 14.25a3 3 0 00-3 3h15.75m-12.75-3h11.218c1.121-2.3 2.1-4.684 2.924-7.138a60.114 60.114 0 00-16.536-1.84M7.5 14.25L5.106 5.272M6 20.25a.75.75 0 11-1.5 0 .75.75 0 011.5 0zm12.75 0a.75.75 0 11-1.5 0 .75.75 0 011.5 0z" />
                            </svg>
                        </button>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<style scoped>
</style>
