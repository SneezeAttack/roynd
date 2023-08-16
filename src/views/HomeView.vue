<template>
  <div class="home">
    <Top />
    <PeopleList />
    <Footer />
  </div>
</template>

<script>
// @ is an alias to /src
import PeopleList from '@/components/PeopleList.vue'
import Top from '@/components/Top.vue'
import Footer from '@/components/Footer.vue'

export default {
  name: 'HomeView',
  components: {
    Top,
    PeopleList,
    Footer
  }
}
</script>
