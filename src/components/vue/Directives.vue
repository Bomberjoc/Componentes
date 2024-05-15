<script setup>
    import { ref } from 'vue';

    let msg = ref('Soy un tooltip');
    let checked = ref(false)
    // let border_color = "border-red-500
    
    let data = ["Hola", "mundo", "cruel"]
    let filtered = data.filter((word) => word.includes('o'))

    let filtered2 = data.filter(function(word) {
        return word.includes('m')
    })
</script>

<template>
    <input 
    class="border"
    :class="{'border-red-500':checked}"
    v-model="msg"
    />
    <div :title="msg">
        {{ msg }}
    </div>
    <label for="check">Seleccionado {{ checked }}</label>
    <input type="checkbox" v-model="checked">

<ul>
    <div class="h-[10px]"></div>
    <li class="text-green-700" v-for="(word, index) in filtered">{{(index+1) +" "+ word }}</li>
    <div class="h-[10px]"></div>
    <li class="text-red-700" v-for="(word, index) in filtered2">{{(index+1) +" "+  word }}</li>
    <div class="h-[10px]"></div>
    <li class="text-blue-700" v-for="(text, index) in data" :key="index">
        {{(index+1) +" "+ text }}
    </li>
</ul>
</template>