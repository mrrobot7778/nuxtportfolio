<template>
  <h2>Comments:</h2>
  <article class="comments px-4 py-4">
    <div class="comment py-4" v-for="item in userData" :key="item.id">
      <div class="avatar">
        <picture>
          <img :src="item.avatar" alt=""/>
        </picture>
      </div>
      <div class="user-data">
        <div class="name">
          {{ item.name }}
        </div>
        <div class="date">
            <date :datetime="item.createdAt.substring(0,10)">{{ item.createdAt.substring(0,10) }}</date>
        </div>
        <div class="comment">
          {{ item.comment }}
        </div>
      </div>
    </div>
  </article>
</template>


<script setup>
    const {data} = await useFetch("https://62fe137ba85c52ee482f275b.mockapi.io/api/v1/comments")
    const userData = reactive(data._value)
    console.log(data)
</script>


<style>

  .avatar picture img {
    width: 50%;
  }

  .comment {
    display: flex;
  }


</style>