<template>
  <Header v-show="route.href !== '/'"/>
  <NuxtLayout>
    <NuxtPage/>
  </NuxtLayout>
  <Footer v-show="route.href !== '/'"/>
</template>

<script setup>
   const route = useRoute();
   console.log(route)
</script>  

<style>
 

  footer {
    height:100px;
  }
</style>