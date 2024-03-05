<template>
    <section class="articles">
      <h2>Posts</h2>
      <ul>
        <li v-for="item in articles" :key="articles.id" class="py-4 px-4">
          <article class="post">
            <header class="py-2">
              <h3>{{ item.title[0].toUpperCase() + item.title.substring(1,item.title.length) }}</h3>
              <span>Created at: <date :datetime="item.createdAt.substring(0,10)">{{ item.createdAt.substring(0,10) }}</date> by <span style="color:blue">James</span></span>
            </header>
            <section class="article px-3 py-3">
              {{item.content.substring(0,200) + "..."}}
            </section>
            <br>
            <NuxtLink :to="item.slug">continue in reading...</NuxtLink>
          </article>
        </li>
      </ul>
    </section>
</template>

<script setup>
   const {data} = await useFetch("https://62fe137ba85c52ee482f275b.mockapi.io/api/v1/posts")
   const articles = reactive(data._value)

</script>

<style lang="scss" scoped>
  
 a {
  text-decoration: none;
  color:blue;
 }

 li {
  list-style-type: none;
 }

 .post {
   border-bottom:1px solid grey;
   background:#F3F3F3;
   padding-bottom:2rem;
   padding-left:2rem;
   padding-right: 2rem;
 }

 .articles {
  width:75%;
 }

 .article {
   background:#FCFCFC;
 }

</style>