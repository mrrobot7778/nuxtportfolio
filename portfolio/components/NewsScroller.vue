<template>
    <div class="d-flex justify-content-center gap-3 container-fluid news-scroller py-3">
       <div class="card scroller-item w-100 flex-row-reverse">
        <img src="../asssets/Snímek obrazovky (11).png" alt="">
         <div class="card-body">
            <h2 class="card-title">Title</h2>
            <time datetime="2024-03-03T08:00:00">March 3, 2024</time>
          <div class="card-text">
            Some text in here
          </div>
         </div>
       </div>
       <div class="card scroller-item w-100">
         <div class="card-body">
            <h2 class="card-title">Title</h2>
            <time datetime="2024-03-03T08:00:00">March 3, 2024</time>
          <div class="card-text">
            Some text in here
          </div>
         </div>
       </div>
    </div>
</template>

<script setup>
     const {data} = await useFetch("https://62fe137ba85c52ee482f275b.mockapi.io/api/v1/posts")

</script>

<style>

  img {
    width:40%;
  }

</style>