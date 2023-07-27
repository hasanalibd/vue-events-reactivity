<script setup>
import { ref, reactive } from 'vue';

const lights = reactive([
  {
    onAndOff:true,
  },
  {
    onAndOff:true,
  },
  {
    onAndOff:true,
  }
])


const message = ref("Make These Buttons Work");
const lighON  = "//img.icons8.com/?size=512&id=12244&format=png";
const lighOFF = "//img.icons8.com/?size=512&id=75&format=png";

function toggle(index)
{
  lights[index].onAndOff = !lights[index].onAndOff;
  message.value   = lights[index].onAndOff?`Light ${index+1} is On`:`Light ${index+1} is Off`;
}

</script>

<template>
  <section class="container mx-auto flex items-center flex-col">
        <h1 class="text-center fs-2 py-10">Simple Vue Js Project</h1>
        <p class="p-5">{{ message }}</p>
        <div class="flex justify-between space-x-6">
            <div class="p-10 border w-96 flex flex-col space-y-5">
                <button @click="toggle(0)" :class="lights[0].onAndOff?'bg-blue-500':'bg-gray-500'" class="text-white font-bold py-2 px-4 rounded">
                    Light 1 {{ lights[0].onAndOff?'On':'Off'  }}
                </button>
                <button @click="toggle(1)" :class="lights[1].onAndOff?'bg-blue-500':'bg-gray-500'" class="text-white font-bold py-2 px-4 rounded">
                    Light 2 {{ lights[1].onAndOff?'On':'Off' }}
                </button>
                <button @click="toggle(2)" :class="lights[2].onAndOff?'bg-blue-500':'bg-gray-500'" class="text-white font-bold py-2 px-4 rounded">
                    Light 3 {{ lights[2].onAndOff?'On':'Off' }}
                </button>
            </div>
            <div class="p-10 border w-96 flex flex-col space-y-5">
                <img class="w-20" :src="lights[0].onAndOff?lighON:lighOFF">
                <img class="w-20" :src="lights[1].onAndOff?lighON:lighOFF">
                <img class="w-20" :src="lights[2].onAndOff?lighON:lighOFF">
            </div>
        </div>
    </section>
</template>

<style scoped></style>