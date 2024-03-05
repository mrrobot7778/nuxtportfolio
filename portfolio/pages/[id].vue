<template>
    <article class="container custom px-4 py-4">
        <header class="py-3">
            <h2 class="title">{{ article.title[0].toUpperCase() + article.title.substring(1,article.title.length)}}</h2>
            <span>Created at: <date :datetime="article.createdAt.substring(0,10)">{{ article.createdAt.substring(0,10) }}</date> by <span style="color:blue">James</span></span>
        </header>
        <section class="article py-3">
            <div class="opener">
              <p>Lorem, ipsum dolor sit amet consectetur adipisicing elit. Nemo eum necessitatibus natus quod eligendi neque iste aspernatur excepturi alias! Corrupti nobis laboriosam itaque alias. Consequatur voluptates aut atque nostrum nemo!</p>
            </div>
            <figure style="text-align: center;">
                <img :src="article.image" alt=""/>
            </figure>
            <div class="main-content">
                <p>{{ article.content }}</p>
                <p>Lorem ipsum dolor, sit amet consectetur adipisicing elit. Eligendi animi qui itaque expedita numquam natus voluptatibus, quasi repellendus magni eius tenetur harum dolorem voluptates atque veritatis perferendis eaque sunt molestiae?</p>
                <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Dolorem porro molestiae iste quo asperiores ad laboriosam vel. Rem aliquam modi quia aut architecto fugit ea esse ratione? Dolores, ducimus molestiae.</p>
            </div>
        </section>
        <Comments/>
    </article>
</template>


<script setup>
  const route = useRoute();
  const {data} = await useFetch("https://62fe137ba85c52ee482f275b.mockapi.io/api/v1/posts")
  const articles = reactive(data._value)
  const article = articles.find((article) => article.slug === route.params.id)
  console.log(article)



</script>

<style scoped>
  header {
    border-bottom:1px solid grey
  }

 figure img {
    width: 60%;
 }

  .custom {
    background:#F9F9F9;
    width: 60%;
  }
  .main-content {
    width:80%;
    margin:0 auto
  }

  .opener {
    width:90%;
    margin:0 auto;
  }

</style>