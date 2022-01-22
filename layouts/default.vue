<template>
  <div>
    <Navbar />
    <div class="container mx-auto">
      <Nuxt />
    </div>
    <Footer />
  </div>
</template>

<script>
import Navbar from '@/components/Navbar'
import Footer from '@/components/Footer'

export default {
  name: 'DefaultLayout',
  components: {
    Navbar,
    Footer
  }
}
</script>
