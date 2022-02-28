<template>
  <div id="app">
    <div class="container">
      <h1 class="mb-4">List Kontak</h1>
      <hr>

      <list-kontak 
        v-bind:customers='customers' 
        @edit-customer="editCustomer"
        @delete-customer="deleteCustomer"
      />

        <div class="card card-body">
          <h2>Form Input Kontak</h2>
          <hr>

          <customer-form @add-customer="addCustomer"/>

        </div>
      
    </div>
  </div>
</template>


<script>
import ListKontak from '@/components/ListKontak.vue'
import CustomerForm from '@/components/KontakForm.vue'

export default {
  name: 'App',
  components: {
    ListKontak,
    CustomerForm, 
  },
  data() {
    return {
      customers: [
        {
          id: 1,
          name: 'Bambang',
          nohp: 1234567890,
          email: 'bambang@mail.com',
          address: 'Jl.Kenanga',
        },
        {
          id: 2,
          name: 'Dika',
          nohp: 1234567890,
          email: 'dika@mail.com',
          address: 'Jl.Mangga',
        },
        {
          id: 3,
          name: 'Agus',
          nohp: 1234567890,
          email: 'agus@mail.com',
          address: 'Jl.Mataram',
        },
         {
          id: 4,
          name: 'Agustin',
          nohp: 1234567890,
          email: 'agus@mail.com',
          address: 'Jl.Mataram',
        },
      ],
    }
  },
  methods: {
    addCustomer(customer) {
      this.customers.push(customer);
    },
    editCustomer(id, data) {
      this.customers = this.customers.map(function (customer) { 
        return customer.id === id ? data : customer;
      });
    },
    deleteCustomer(id) {
      this.customers = this.customers.filter(function (customer) { 
        return customer.id !== id;
      });
    }
  }
}
</script>

<style scoped>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: left;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
