<template>
  <footer>
    <div class="col">
      <div class="row row-1">
        <div class="media-icons">
          <NuxtLink class="header" to="/">
            ARBlogs
          </NuxtLink>
          <ul class="icons">
            <li>
              <a href="https://github.com/atakanreyhanioglu">
                <git-hub-icon class="svg-icon"></git-hub-icon>
              </a>
            </li>
            <li>
              <a href="https://medium.com/@atakan.reyhanioglu">
                <medium-icon class="svg-icon"></medium-icon>
              </a>
            </li>
            <li>
              <a href="https://www.linkedin.com/in/atakan-reyhanio%C4%9Flu-631730185/">
                <linked-in-icon class="svg-icon"></linked-in-icon>
              </a>
            </li>
            <li>
              <a href="https://www.instagram.com/ataa_ata/">
                <instagram-icon class="svg-icon"></instagram-icon>
              </a>
            </li>
          </ul>
        </div>
      </div>
      <div class="row row-2">
        <ul class="ul-links">
          <NuxtLink to="/" class="link-footer">Home</NuxtLink>
          <NuxtLink to="/blogs" class="link-footer">Blogs</NuxtLink>
          <NuxtLink to="/create-post" v-if="user" class="link-footer">Create Post</NuxtLink>
          <NuxtLink to="/login" v-if="!user" class="link-footer">Login In | Register</NuxtLink>
        </ul>
      </div>
      <div class="row row-3">
        <p>&copy; Copyright 2022 All Rights Reserved.</p>
      </div>
    </div>
  </footer>
</template>
<script>
import gitHubIcon from '../assets/icons/gitHub.svg'
import linkedInIcon from '../assets/icons/linkedin.svg'
import instagramIcon from '../assets/icons/instagram.svg'
import mediumIcon from '../assets/icons/medium.svg'

export default {
  name: 'FooterComponent',
  components: {
    linkedInIcon,
    instagramIcon,
    gitHubIcon,
    mediumIcon
  }
}
</script>
<style>
 .svg-icon {
   width: 35px;
   height: 32px;
 }
 .col {
   width: 100%;
   display: flex;
 }
 .row {
   width: 100%;
   height: 240px;
   display: flex;
   flex-direction: column;
   justify-content: center;
   align-items: center;
 }
 .icons {
   display: flex;
   gap: 14px;
   margin-top: 35px;
 }
 .ul-links {
   display: flex;
   flex-direction: column;
   gap: 10px;
   font-weight: 500;
   font-size: 18px;
 }
 .row-3 {
    padding-top: 50px;
 }
 @media screen and (max-width: 750px) {
   .col {
     flex-direction: column;
     gap: 0;
   }
   .row {
     height: 150px;
   }
   .icons {
     gap: 5px
   }
   .row-3 {
     padding: 0;
     height: 40px;
   }
 }
</style>
