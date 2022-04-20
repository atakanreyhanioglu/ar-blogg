<template>
  <div class="container">
    <NavigationComponent class="nav"></NavigationComponent>
    <div class="content">
      <BlogPost :post="welcomeScreen"/>
      <BlogPost :post="post" v-for="(post, index) in sampleBlogPost" :key="index"/>
    </div>
    <FooterComponent class="footer"></FooterComponent>
  </div>
</template>

<script>
import NavigationComponent from "@/components/navigation";
import FooterComponent from "@/components/footer";
export default {
  name: 'HomePage',
  components: {FooterComponent, NavigationComponent},
  data() {
    return {
      welcomeScreen: {
        title: "WELCOME!",
        blogPost: "Weekly blog articles with all things programming including HTML, CSS, JavaScript and more. Register today to never miss a post!",
        welcomeScreen: true,
        photo: 'cover-image'
      },
      sampleBlogPost: [
        {
          title: "This is a Filler Title!2",
          blogHTML: "This is a filler blog post title!",
          blogCoverPhoto: "blogImage"
        },
        {
          title: "This is a Filler Title!",
          blogHTML: "This is a filler blog post title!",
          blogCoverPhoto: "blogImage"
        }
      ]
    }
  }
}
</script>
<style>
.container {
  display: flex;
  flex-direction: column;
  justify-content: center;
}
.content {
  width: 100%;
  height: 100vh;
}
.footer {
  background-color: whitesmoke;
}
</style>
