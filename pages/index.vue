<template>
  <div class="container">
    <NavigationComponent class="nav"></NavigationComponent>
    <div class="content">
    </div>
    <FooterComponent class="footer"></FooterComponent>
  </div>
</template>

<script>
import NavigationComponent from "@/components/navigation";
import FooterComponent from "@/components/footer";
export default {
  name: 'HomePage',
  components: {FooterComponent, NavigationComponent}
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
