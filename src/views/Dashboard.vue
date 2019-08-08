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
          @click:row="toggleSnackbar"
        ></v-data-table>
      </v-card-text>
    </v-card>
    <v-snackbar
      v-model="snackbar"
    >
      You've selected {{ selectedEmployee }}
      <v-btn
        color="pink"
        text
        @click="snackbar = false"
      >
        Close
      </v-btn>
    </v-snackbar>
  </div>
</template>

<script>
import employeeData from '../data/employees.json'

export default {
  name: 'Dashboard',
  methods: {
    toggleSnackbar(event) {
      debugger
      this.snackbar = true
      this.selectedEmployee = event.name
    }
  },
  data() {
    return {
      selectedEmployee: '',
      snackbar: true,
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
