<template>
   <section class="container-fluid post-info">
    <header class="py-3">
        <h1>Title</h1>
    </header>
    <section class="py-1 descripion w-50">
      <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Nulla libero, et ducimus, in provident facere fuga doloribus praesentium harum recusandae eveniet numquam ex vitae nemo dolore voluptatum vel repellat. Non!</p>
      <NuxtLink class="py-2" to="/">continute reading...</NuxtLink>
    </section>
   </section>
</template>


<script setup>
  
</script>


<style scoped>

  h1 {
    font-size: 4.5rem;
  }

  p {
    font-size: 1.3rem;
  }

  .post-info {
    background: #25242A;
    color:white;
    padding-left:3rem;
  }
 
</style>