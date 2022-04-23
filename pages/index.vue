<template>
    <div class="container">
      <NavigationComponent class="nav"></NavigationComponent>
      <div class="content">
        <BlogPost :post="welcomeScreen"/>
        <BlogPost :post="post" v-for="(post, index) in sampleBlogPost" :key="index"/>
        <div class="blog-card-wrap">
        <div class="container">
          <h3>View More Recent Blogs</h3>
          <div class="blog-cards">
             <BlogCard :post="post" v-for="(post, index) in sampleBlogCards" :key="index"></BlogCard>
          </div>
        </div>
        </div>
      </div>
    <FooterComponent></FooterComponent>
  </div>
</template>

<script>
import BlogPostComponent from '@/components/blogPost'
import NavigationComponent from "@/components/navigation";
import FooterComponent from "@/components/footer";
import BlogCardComponent from "@/components/blogCard"
export default {
  name: 'HomePage',
  components: {NavigationComponent, BlogPostComponent, BlogCardComponent, FooterComponent},
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
          blogCoverPhoto: "last-image"
        },
        {
          title: "What is my duties as a programmer?",
          blogHTML: "Should I take care about all the project by myself or manage it with my team?",
          blogCoverPhoto: "blog-image"
        }
      ],
      sampleBlogCards: [
        {blogTitle: 'Blog Card #1',blogCoverPhoto: 'stock-1', blogDate: 'May 1, 2022' },
        {blogTitle: 'Blog Card #2',blogCoverPhoto: 'stock-2', blogDate: 'May 2, 2022' },
        {blogTitle: 'Blog Card #3',blogCoverPhoto: 'stock-3', blogDate: 'May 3, 2022' },
        {blogTitle: 'Blog Card #4',blogCoverPhoto: 'stock-4', blogDate: 'May 4, 2022' }
      ]
    }
  }
}
</script>
<style scoped>
.container {
  display: flex;
  flex-direction: column;
  justify-content: center;
}
.content {
  width: 100%;
}
h3 {
  font-weight: 300;
  font-size: 42px;
  margin-bottom: 32px;
}
</style>
