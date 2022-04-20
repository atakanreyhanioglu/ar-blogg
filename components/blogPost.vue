<template>
  <div class="blog-wrapper">
    <div class="blog-content">
      <div class="home-col-1">
        <h2 v-if="post.welcomeScreen">{{ post.title }}</h2>
        <h2 v-else>{{ post.title }}</h2>
        <p v-if="post.welcomeScreen">{{ post.blogPost }}</p>
        <p class="content-preview" v-else>{{ post.blogHTML }}</p>
        <NuxtLink to="#" class="post-detail" v-if="post.welcomeScreen">
          Login/Register
          <Arrow class="arrow"/>
        </NuxtLink>
        <NuxtLink class="post-detail link link-light" to="" v-else>
          View The Post
          <Arrow class="arrow"/>
        </NuxtLink>
      </div>
      <div class="home-col-2">
        <img v-if="post.welcomeScreen" :src="require(`../assets/blogPhotos/${post.photo}.png`)"
             alt="cover picture for welcome screen."/>
        <img v-else :src="require(`../assets/blogPhotos/${post.blogCoverPhoto}.jpg`)" alt="cover image for blog post."/>
      </div>
    </div>
  </div>

</template>
<script>
import Arrow from 'vue-material-design-icons/ArrowRight.vue'

export default {
  name: 'BlogPostComponent',
  props: ["post"],
  components: {
    Arrow
  }
}
</script>
<style>
.blog-content {
  display: flex;
  height: 90vh;
  width: 100%;
  justify-content: center;
  align-items: center;
  background-color: #303030;
}

.home-col-1 {
  padding: 40px 80px;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: flex-start;
  gap: 30px;
  width: 50%;
}

h2, p {
  color: white;
}

p {
  font-weight: 150;
  font-size: 16px;
}

h2 {
  font-weight: 300;
  font-size: 44px;
}

.home-col-2 {
  width: 50%;
  display: flex;
  justify-content: center;
  flex-direction: column;
  align-items: flex-start;
  height: 100vh;
}

img {
  border-radius: 4px;
  width: 90%;
  height: auto;
  min-width: 300px;
}

.post-detail {
  display: flex;
  align-items: center;
  justify-content: flex-start;
  gap: 5px;
  cursor: pointer;
  text-decoration: none;
  text-transform: uppercase;
  color: white;
  width: 130px;
  border-bottom: 2px solid transparent;
}

@keyframes increase {
  0% {
    border-bottom: 2px solid #fff;
    width: 5%;
  }
  100% {
    border-bottom: 2px solid #fff;
    width: 130px;
  }
}

.post-detail:hover {
  animation: increase 1s;
  animation-fill-mode: forwards;
}

@media screen and (max-width: 750px) {
  .blog-content {
    flex-direction: column-reverse;
  }

  img {
    padding-top: 40px;
    width: 100%;
    height: 100%;
  }

  .home-col-1 {
    width: 100%;
    gap: 10px;
  }

  .home-col-2 {
    width: 100%;
  }
  .blog-content {
    height: 85vh;
  }
}

</style>
