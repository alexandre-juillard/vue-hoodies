<script setup>
import {ref} from "vue"
const props = defineProps({
    hoodie:{
        type:Object
    }
})


const allSizes = ref([0,0,0,0])

const handleSizeBtn = (index)=>{
    // console.log(index)
    
    let shouldReset = false
    if(allSizes.value[index]){
        shouldReset = true
    }
    // je reset tout
    allSizes.value.forEach((btn,idx)=>{
        allSizes.value[idx]=0
    })
    // je remet à true que celui séléctionné
    if(!shouldReset){
        allSizes.value[index] = 1
    }
    
    console.log(allSizes.value)
}

const handleAddToCart = ()=> {
    // sa taille 
    const findTaille = allSizes.value.findIndex((size)=>size==1)

    console.log({findTaille})

    // récupère la ref du hoodie ? 
    
    // la quantité 
    // emit pour dire à l'app.vue que ce hoodie et ces options ont été ajoutées 

}


</script>

<template>
  <div class="flex w-full border-b-2 border-tertiary-contrast mt-6">
        <div
        class="flex rounded-lg bg-card-background-light shadow-lg flex-row w-full">
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
                    @click="handleSizeBtn(0)"
                    type="button"
                    :class="allSizes[0]?'border-button-text':'border-tertiary-contrast'"
                    class="inline-block rounded border-2  border-opacity-75 px-6 pt-2 pb-2 text-xs font-medium uppercase leading-normal text-info "
                >
                    S
            </button>
            
            <button 
                    @click="handleSizeBtn(1)"
                    type="button"
                    :class="allSizes[1]?'border-button-text':'border-tertiary-contrast'"
                    class="inline-block rounded border-2  border-opacity-75 px-6 pt-2 pb-2 text-xs font-medium uppercase leading-normal text-info "
                    > <!-- exemple quand la taille est séléctionnée vvvv   -->
                    M
            </button>
            <button
                @click="handleSizeBtn(2)"
                type="button"
                :class="allSizes[2]?'border-button-text':'border-tertiary-contrast'"
                class="inline-block rounded border-2   border-opacity-75 px-6 pt-2 pb-2 text-xs font-medium uppercase leading-normal text-info "
            >
                L
            </button>
            <button
                 @click="handleSizeBtn(3)"
                type="button"
                :class="allSizes[3]?'border-button-text':'border-tertiary-contrast'"
                class="inline-block rounded border-2   border-opacity-75 px-6 pt-2 pb-2 text-xs font-medium uppercase leading-normal"
            >
                XL
            </button>
            </p>
            <div class="flex flex-row mt-12">
                <div class="basis-1/4 w-96">
                    QTY
                    <select >
                        <option value="0">0</option>
                        <option value="1" selected>1</option>
                        <option value="2">2</option>
                        <option value="3">3</option>
                        <option value="4">4</option>
                        <option value="5">5</option>
                        <option value="6">6</option>
                        <option value="7">7</option>
                        <option value="8">8</option>
                    </select>
                </div>
                <div class="basis-1/4">
                    <button
                        type="button"
                        @click="handleAddToCart"
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
