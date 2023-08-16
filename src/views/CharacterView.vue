<template>
	<div class="character">
		<Top />
		<Character />
		<Footer />
	</div>
</template>

<script>
// @ is an alias to /src
import Character from '@/components/Character.vue'
import Top from '@/components/Top.vue'
import Footer from '@/components/Footer.vue'

export default {
  name: 'CharacterView',
  components: {
    Character,
	Top,
	Footer
  }
  }
  </script>