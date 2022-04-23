<template>
 <div class="blog-card blog-card-style">
   <div class="icons">
     <div class="icon">
       <Edit class="icon">

       </Edit>
     </div>
     <div class="icon">
       <Delete class="icon">

       </Delete>
     </div>
   </div>
   <img class="card-image" :src="require(`../assets/blogCards/${post.blogCoverPhoto}.jpeg`)" alt="blog cards photos.">
   <div class="card-info">
     <div class="text-infos">
       <h4>{{post.blogTitle}}</h4>
       <h6>Posted on: {{post.blogDate}}</h6>
     </div>
     <NuxtLink class="link link-post" to="#">
       View The Post <Arrow class="arrow"></Arrow>
     </NuxtLink>
   </div>
 </div>

</template>
<script>
import Arrow from 'vue-material-design-icons/ArrowRight.vue'
import Edit from 'vue-material-design-icons/SquareEditOutline.vue'
import Delete from 'vue-material-design-icons/Delete.vue'


export default {
  name: 'BlogCardComponent',
  props: ["post"],
  components: {
    Arrow,
    Edit,
    Delete
  }
}
</script>
<style>
.card-info {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  justify-content: space-between;
  height: 100%;
  padding: 10px;
}
.blog-card {
  display: flex;
  flex-direction: column;
}
.blog-card-style {
  position: relative;
  cursor:pointer;
  border-radius: 8px;
  background-color: #fff;
  min-height: 380px;
  transition: .5s ease all;
}
.blog-card-style:hover {
  transform: rotateZ(-1deg) scale(1.01);
  box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1), 0 2px 4px -1px rgba(0, 0, 0, 0.06);
}
.icons {
  position: absolute;
  top: -26px;
  right: 8px;
  z-index: 98;
}
.icons > .icon {
  display: flex;
  justify-content: center;
  align-items: center;
  width: 35px;
  height: 35px;
  border-radius: 50%;
  background-color: white;
  transition: 0.5s ease all;
}
.icons > .icon:hover {
  background-color: #303030;
  color: white;
}
.card-image {
  width: 100%;
  margin-bottom: 10px;
}
.link-post {
  font-size: 16px;
  display: flex;
  justify-content: center;
  align-items: center;
}

</style>
