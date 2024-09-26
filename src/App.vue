<template>

   <div id="app"> 
  <InpuAdd /> <!-- To'g'ri komponent chaqirilganligini tekshiring -->
</div>
</template>

<script>
import InpuAdd from '@/components/InpuAdd.vue'; // To'g'ri import

export default {
    name: 'App',
    components: {
        InpuAdd, // Komponentni to'g'ri ro'yxatga oling
    },
};
</script>

<style>
/* Stilingiz bu yerda bo'lishi mumkin */
</style>
