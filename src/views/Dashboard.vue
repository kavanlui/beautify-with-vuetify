<template>
  <div>
    <v-card class="ma-5">
      <v-card-title>
        <h1 class="display-1">Dashboard</h1>
      </v-card-title>
      <v-card-text>
        <v-data-table
          :headers="headers"
          :items="employees"
          :items-per-page="5"
          class="elevation-1"
          @click:row="action"
        ></v-data-table>
      </v-card-text>
  </v-card>
  </div>
</template>

<script>
import employeeData from '../data/employees.json'

export default {
  name: 'Dashboard',
  methods: {
    action(ev) {
      console.log(this.currentItems)

    }
  },
  data() {
    return {
      headers: [
        {
          text: 'ID',
          value: 'id'
        },
        {
          text: 'Name',
          value: 'name'
        },
        {
          text: 'Title',
          value: 'title'
        },
        {
          text: 'Salary',
          value: 'salary'
        }
      ],
      employees: employeeData,
      value: [
        423,
        446,
        675,
        510,
        590,
        610,
        760,
      ],

    }
  }
}
</script>

<style>

</style>
