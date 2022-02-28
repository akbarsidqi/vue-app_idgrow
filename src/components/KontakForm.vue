<template>
  <div class="kontak-form">
    <form @submit.prevent="submit">
      <div class="form-group">
        <label for="name">Nama</label>
        <input type="text" v-model="customer.name" class="form-control" placeholder="">
      </div>
      <div class="form-group">
        <label for="nohp">No HP</label>
        <input type="text" v-model="customer.nohp" class="form-control" placeholder="">
      </div>
      <div class="form-group">
        <label for="email">Email</label>
        <input type="text" v-model="customer.email" class="form-control" placeholder="">
      </div>
      <div class="form-group">
        <label for="address">Alamat</label>
        <textarea type="text" v-model="customer.address" class="form-control" 
          placeholder=""> </textarea>
      </div><br>
      <button type="submit" class="btn btn-primary mr-2">Submit</button> &nbsp;
      <button class="btn btn-danger" type="button" data-toggle="collapse" data-target="#collapseExample">
        Cancel
        </button>
    </form>
  </div>
</template>

<script>
  export default {
    name: 'customer-form', 
    data(){
      return {
        customer: {
          name: '',
          email: '',
          address: '',
        }
      }
    },
    methods: {
      submit() {
        this.$emit('add-customer', this.customer)
        this.customer = {
          name: '',
          email: '',
          address: '',
        }
      },
    },
  }
</script>