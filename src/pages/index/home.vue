<template>
	<div class="bg-img responsive img-responsive">
		<b-container fluid>
			<b-row>
				<h1 class="d-none">iVista</h1>
				<section class="w-100 text-center">
					<home-banner></home-banner>
				</section>
			</b-row>
		</b-container>
	</div>
</template>

<script>
import HomeBanner from '@/components/Home.Banner'
import Vue from 'vue'
import VueBus from 'vue-bus'

import bContainer from 'bootstrap-vue/es/components/layout/container'

import { Layout } from 'bootstrap-vue/es/components'
Vue.use(VueBus)
Vue.component('b-container', bContainer)
Vue.use(Layout)

export default {
  name: 'hello',
  components: {
    HomeBanner
  },
  data () {
    return {
      name: 'iVista',
      showAlert: true,
      text: `
        iVista.
        `
    }
  }
}
</script>