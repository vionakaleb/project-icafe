<template>
	<div class="bg-img responsive img-responsive">
    <b-container>
        <div class="pt-5" align="center">
          <FormIcafe class="mb-0"></FormIcafe>
        </div>

        <!-- <div class="col-md-6 mt-4">
              <FormOwner class="w-100 mb-3"></FormOwner>         
        </div> -->

    </b-container>
  </div>
</template>

<script>
import FormIcafe from '@/components/Form.icafe'
import Vue from 'vue'
import VueBus from 'vue-bus'

Vue.use(VueBus)

export default {
  name: 'form',
  components: {
    FormIcafe
  },
  data () {
    return {
      name: 'Form',
      showAlert: true,
      text: `
        Anim pariatur cliche reprehenderit, enim eiusmod high life accusamus terry
        richardson ad squid. 3 wolf moon officia aute, non cupidatat skateboard dolor
        brunch. Food truck quinoa nesciunt laborum eiusmod.
        `
    }
  }
}
</script>

<style>
label {display:block;clear:both;}

.ml-custom
{
  margin-left:1px;
}
</style>