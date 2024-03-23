<script setup>
import {HOODIES} from './assets/js/hoodies'

console.log(HOODIES)

</script>

<template>

    <nav class="w-full border-b-2 border-tertiary-contrast sticky top-0 bg-card-background-light">
            <div class="grid grid-cols-3 items-center h-16 ">
                <div class=" ml-8 "><img src="./img/streamlit.svg" alt="" class="object-cover h-12"/></div>
                <div class=" justify-self-center space-x-6">
                    <a href="#" class="">Pricing</a>
                    <a href="#" class="">Product</a>
                </div>
                <div class=" justify-self-end mr-8">
                    <svg  xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-6 h-6">
                        <path stroke-linecap="round" stroke-linejoin="round" d="M2.25 3h1.386c.51 0 .955.343 1.087.835l.383 1.437M7.5 14.25a3 3 0 00-3 3h15.75m-12.75-3h11.218c1.121-2.3 2.1-4.684 2.924-7.138a60.114 60.114 0 00-16.536-1.84M7.5 14.25L5.106 5.272M6 20.25a.75.75 0 11-1.5 0 .75.75 0 011.5 0zm12.75 0a.75.75 0 11-1.5 0 .75.75 0 011.5 0z" />
                    </svg>
                    
                </div>
            </div>
    </nav>
  <div id='filters' class="container mx-auto w-2/3">
    <div class="px-4 mt-4 flex space-x-2">
            <span
                class="inline-block whitespace-nowrap rounded-[0.27rem] cursor-pointer bg-tertiary-contrast px-[0.65em] pt-[0.35em] pb-[0.30em] text-center align-baseline text-[0.75em] leading-none text-card-background-light">
                All ⚪
            </span>
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
  </div>
  <div class="container mx-auto mt-4  w-2/3 bg-card-background rounded py-2">
        
        
    <div id="item-list" class="px-4 ">
        <!-- item card -->
        <div class="flex w-full border-b-2 border-tertiary-contrast mt-6">
            <div class="flex rounded-lg bg-card-background-light shadow-lg flex-row w-full">
                <img
                    class="h-96 w-full rounded-t-lg object-cover md:h-auto md:w-48 md:rounded-none md:rounded-l-lg"
                    src="https://cdn.shopify.com/s/files/1/0550/6996/6414/products/6560_1800x.jpg?v=1645098113"
                    alt="" />
                <div class="flex flex-col justify-start p-6">
                    <h5   class="mb-2 text-2xl font-bold text-neutral-800">
                        Dedicated Fallun
                        <span  class="inline-block ml-4 bg-button-background  border-button-text rounded-md border-2 border-primary px-6 py-2  text-sm font-bold uppercase leading-normal text-primary ">
                            100 € 
                        </span>
                    </h5>

                    <p class="mb-4 text-base text-neutral-600">
                        Hoodie made in soft sweatshirt fabric with the highest quality Organic and Fairtrade cotton
                    </p>
                    <p class="text-xs text-neutral-600 space-x-1">
                        <!-- bouton disable si pas en stock -->
                        <button
                            type="button"
                            disabled
                            class="disabled:opacity-50 inline-block rounded border-2  border-opacity-75 px-6 pt-2 pb-2 text-xs font-medium uppercase leading-normal text-info border-tertiary-contrast"
                        >
                            S
                        </button>
                        <button
                            type="button"
                            class="inline-block rounded border-2  border-opacity-75 px-6 pt-2 pb-2 text-xs font-medium uppercase leading-normal text-info border-tertiary-contrast"
                        >
                            M
                        </button>
                        <button
                            type="button"
                            class="inline-block rounded border-2  border-opacity-75 px-6 pt-2 pb-2 text-xs font-medium uppercase leading-normal text-info border-paragraph-black"
                        >
                            L
                        </button>
                        <button
                            type="button"
                            class="inline-block rounded border-2  border-opacity-75 px-6 pt-2 pb-2 text-xs font-medium uppercase leading-normal text-info border-tertiary-contrast"
                        >
                            xl
                        </button>
                    </p>
                    <div class="flex flex-row mt-8">
                        <div class="basis-1/4">
                            <button
                                type="button"
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
        
    </div>

</div>
<div
        class="fixed inset-0 bg-gray-600 bg-opacity-50 overflow-y-auto h-full w-full hidden"
    >
    <!-- modal, active/désactive en enlevant la class 'hidden' -->
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
