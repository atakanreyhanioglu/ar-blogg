<template>
    <div class="container">
      <NavigationComponent class="nav"></NavigationComponent>
      <div class="content">
        <BlogPost :post="welcomeScreen"/>
        <BlogPost :post="post" v-for="(post, index) in sampleBlogPost" :key="index"/>
      </div>
    <FooterComponent></FooterComponent>
  </div>
</template>

<script>
import BlogPostComponent from '@/components/blogPost'
import NavigationComponent from "@/components/navigation";
import FooterComponent from "@/components/footer";
export default {
  name: 'HomePage',
  components: {NavigationComponent, BlogPostComponent, FooterComponent},
  data() {
    return {
      footerBackground: 'whitesmoke',
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
          blogCoverPhoto: "last-image"
        },
        {
          title: "What is my duties as a programmer?",
          blogHTML: "Should I take care about all the project by myself or manage it with my team?",
          blogCoverPhoto: "blog-image"
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
}
</style>
