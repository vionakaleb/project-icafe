<template>
  <div>
    <b-form @submit="onSubmit" @reset="onReset" v-if="show" align=left>
      <b-row>
      <div class="col-md-6 mb-4">
      <p class="size-16 light-bold">DATA i-CAFE</p>
      <b-form-group id="InputGroup1" class="font-gray size-13 mb-0"
                    horizontal
                    :label-cols="3"
                    breakpoint="md"
                    label="Nama i-Cafe:"
                    label-for="Input1">
        <b-form-input id="Input1" class="bg-secondary border-transparent"
                      type="text"
                      size="sm"
                      v-model="form.namaWarnet"
                      required>
        </b-form-input>
      </b-form-group>

      <b-form-group id="InputGroup2" class="font-gray size-13 mb-0"
                    horizontal
                    :label-cols="3"
                    breakpoint="md"
                    label="Alamat i-Cafe:"
                    label-for="Input2">
        <b-form-input id="Input2" class="bg-secondary border-transparent"
                      type="text"
                      size="sm"
                      v-model="form.alamatWarnet"
                      required>
        </b-form-input>
      </b-form-group>

      <b-form-group id="InputGroup3" class="font-gray size-13 mb-0"
                    horizontal
                    :label-cols="3"
                    breakpoint="md"
                    label="No. Telpon:"
                    label-for="Input3">
        <b-form-input id="Input3" class="bg-secondary border-transparent"
                      type="text"
                      size="sm"
                      v-model="form.teleponWarnet"
                      required>
        </b-form-input>
      </b-form-group>

      <b-form-group id="InputGroup4" class="font-gray size-13 mb-0"
                    horizontal
                    :label-cols="3"
                    breakpoint="md"
                    label="Website (Jika Ada):"
                    label-for="Input4">
        <b-form-input id="Input4" class="bg-secondary border-transparent"
                      type="text"
                      size="sm"
                      v-model="form.websiteWarnet">
        </b-form-input>
      </b-form-group>

      <b-form-group id="InputGroup5" class="font-gray size-13 mb-0"
                    horizontal
                    :label-cols="3"
                    breakpoint="md"
                    label="Facebook / IG:"
                    label-for="Input5">
        <b-form-input id="Input5" class="bg-secondary border-transparent"
                      type="text"
                      size="sm"
                      v-model="form.sosmedWarnet"
                      required>
        </b-form-input>
      </b-form-group>

      <b-form-group id="InputGroupPC" class="font-gray size-13 mb-0"
                    horizontal
                    :label-cols="3"
                    breakpoint="md"
                    label="Jumlah PC:"
                    label-for="inputPC">
        <b-form-input id="inputPC" type="number" placeholder="" size="sm"
                      class="bg-secondary border-transparent"
                      v-model="form.jumlahPc"
                      required>
        </b-form-input>             
      </b-form-group>

      <b-form-group id="InputGroupVGA" class="font-gray size-13 mb-0"
                    horizontal
                    :label-cols="3"
                    breakpoint="md"
                    label="Jenis VGA:"
                    label-for="inputVGA">
        <b-form-input id="inputVGA" class="bg-secondary border-transparent"
                      type="text"
                      size="sm"
                      v-model="form.jenisVga"
                      required>
        </b-form-input>
      </b-form-group>

      <!-- <b-form-group id="InputGroupDrop"
                    horizontal
                    :label-cols="3"
                    breakpoint="md"
                    label="dropdown:"
                    label-for="InputDrop">
        <b-form-select id="InputDrop"
                      :options="dropdown"
                      required
                      v-model="form.dropdown">
        </b-form-select>
      </b-form-group> -->

      <label class="font-gray size-13 mt-4">Foto bukti pembelian NVidia GeForce (Min spesifikasi GTX 1050 sebanyak 20pcs):</label>
      <div class="container mb-5">
      <input-image :index="1" @setSelectedImage="setSelectedImage"></input-image>
      </div>     
      </div>

      <div class="col-md-6">
      <p class="size-16 light-bold">DATA PEMILIK</p>
      <b-form-group id="InputGroup6" class="font-gray size-13 mb-0"
                    horizontal
                    :label-cols="3"
                    breakpoint="md"
                    label="Nama pemilik i-Cafe:"
                    label-for="Input6">
        <b-form-input id="Input6" class="bg-secondary border-transparent"
                      type="text"
                      size="sm"
                      v-model="form.namaPemilik"
                      required
                      placeholder="">
        </b-form-input>
      </b-form-group>

      <b-form-group id="InputGroup7" class="font-gray size-13 mb-0"
                    horizontal
                    :label-cols="3"
                    breakpoint="md"
                    label="No HP Pemilik:"
                    label-for="Input7">
        <b-form-input id="Input7" class="bg-secondary border-transparent"
                      type="text"
                      size="sm"
                      v-model="form.teleponPemilik"
                      required
                      placeholder="">
        </b-form-input>
      </b-form-group>

      <b-form-group id="InputGroup8" class="font-gray size-13 mb-0"
                    horizontal
                    :label-cols="3"
                    breakpoint="md"
                    label="E-mail Pemilik:"
                    label-for="Input8">
        <b-form-input id="Input8" class="bg-secondary border-transparent"
                      type="email"
                      size="sm"
                      v-model="form.emailPemilik"
                      required
                      placeholder="">
        </b-form-input>
      </b-form-group>

      <b-form-group id="InputGroupFile3" class="font-gray size-13 mb-0 mt-4"
                    horizontal
                    :label-cols="3"
                    breakpoint="md"
                    label="Foto Tempat Usaha:"
                    label-for="InputFile2">

                    <div class="row ml-3">
                    <input-image :index="2" @setSelectedImage="setSelectedImage"></input-image>
                    </div>  
      </b-form-group>

      <b-form-group id="InputGroupFile3" class="font-gray size-13 mb-0 mt-5"
                    horizontal
                    :label-cols="3"
                    breakpoint="md"
                    label="Foto Tempat Usaha:<br>(Tampak Luar & Dalam)"
                    label-for="InputFile3">
        <div class="row ml-3">
          <div class="col-xs-6">
            <input-image :index="3" @setSelectedImage="setSelectedImage"></input-image>
          </div>
          <div class="col-xs-6">
            <input-image :index="4" @setSelectedImage="setSelectedImage"></input-image>
          </div>
        </div>
      </b-form-group>

      <b-form-group id="GroupChecks" class="font-gray pt-5">
        <b-form-checkbox-group v-model="form.isSubscribe" id="Checks">
          <b-form-checkbox value="true" class="font-gray size-12">Saya ingin mengikuti update terbaru dengan berlangganan Newsletter.</b-form-checkbox>
        </b-form-checkbox-group>
      </b-form-group>

      <b-button type="submit" variant="primary" class="" v-if="!btnSubmit" >Submit Form</b-button>
                <b-button type="submit" variant="primary" class="" v-else disabled>loading..</b-button>
      <!-- <b-button type="reset" variant="danger">Reset</b-button> -->

      </div>

      </b-row>
    </b-form>
  </div>
</template>

<script>
import InputImage from '@/components/Form.InputImage'
import axios from 'axios'
import VueSweetalert2 from 'vue-sweetalert2'
import Vue from 'vue'

Vue.use(VueSweetalert2)

export default {
  components: {
    'input-image': InputImage
  },
  data () {
    return {
      btnSubmit: false,
      form: {
        namaWarnet: '',
        alamatWarnet: '',
        teleponWarnet: '',
        websiteWarnet: '',
        sosmedWarnet: '',
        jumlahPc: '',
        jenisVga: '',
        namaPemilik: '',
        teleponPemilik: '',
        emailPemilik: '',
        isSubscribe: false,
        selectedImages: {
          receipt: '',
          icafeLogo: '',
          locationFront: '',
          locationBehind: ''
        }
      },
      show: true
    }
  },
  methods: {
    onSubmit (evt) {
      evt.preventDefault()
      this.btnSubmit = true
      console.log(JSON.stringify(this.form))
      let isSubscribe = 0
      if (this.form.isSubscribe.length > 0) {
        isSubscribe = 1
      }
      let data = {
        'namaWarnet': this.form.namaWarnet,
        'alamatWarnet': this.form.alamatWarnet,
        'teleponWarnet': this.form.teleponWarnet,
        'sosmedWarnet': this.form.sosmedWarnet,
        'jenisVga': this.form.jenisVga,
        'jumlahPc': this.form.jumlahPc,
        'websiteWarnet': this.form.websiteWarnet,
        'namaPemilik': this.form.namaPemilik,
        'teleponPemilik': this.form.teleponPemilik,
        'emailPemilik': this.form.emailPemilik,
        'isSubscribe': isSubscribe,
        'receipt': this.form.selectedImages.receipt,
        'icafeLogo': this.form.selectedImages.icafeLogo,
        'locationFront': this.form.selectedImages.locationFront,
        'locationBehind': this.form.selectedImages.locationBehind
      }
      axios.post(process.env.API_URL + '/api/v1/register', data)
        .then(response => {
          if (response.data.status) {
            this.$swal('Register Successfull', '', 'success')
            this.$router.push('/home')
            this.form = []
          } else {
            this.btnSubmit = false
            this.$swal({
              type: 'error',
              title: 'Failed to Register',
              html: response.data.errors
            })
          }
        }, response => {
          this.$swal({
            type: 'error',
            title: 'Failed to Register',
            text: 'Please re-check your input'
          })
          this.btnSubmit = false
        })
    },
    onReset (evt) {
      evt.preventDefault()
      /* Reset our form values */
      this.form.email = ''
      this.form.name = ''
      this.form.checked = []
      /* Trick to reset/clear native browser form validation state */
      this.show = false
      this.$nextTick(() => {
        this.show = true
      })
    },
    setSelectedImage (imageUrl, key) {
      if (key === 1) { this.form.selectedImages.receipt = imageUrl } else if (key === 2) { this.form.selectedImages.icafeLogo = imageUrl } else if (key === 3) { this.form.selectedImages.locationFront = imageUrl } else if (key === 4) { this.form.selectedImages.locationBehind = imageUrl }
    }
  }
}
</script>

<!-- b-form-1.vue -->