<template>
  <div class="container">
    <session-details :content="content"/>
  </div>
</template>

<script>
import SessionDetails from '../components/SessionDetails.vue'
export default {
  components: { SessionDetails },  
  async asyncData({ $content, params }) {
      // fetch our content here
      const content = await $content('sessions', "nassim").fetch()
        console.log(content.isPro);
      return { content }
    }
  }

</script>

<style>
.container {
    @apply min-h-screen flex justify-center items-center text-center mx-auto;
}

</style>
