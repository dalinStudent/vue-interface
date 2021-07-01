<template>
  <div class="d-flex flex-column flex-grow-1">
    <div class="d-flex align-center py-3">
      <v-spacer />
      <v-btn
        color="primary"
        height="40"
        to="/staffs/register"
      >
        <v-icon left>mdi-account-multiple-plus</v-icon>
        Add new Staff
      </v-btn>
    </div>
    <v-card class="pa-2">
      <v-row class="pa-2 align-center justify-content-end">
        <v-col cols="6" sm="2" md="6" class="d-flex text-right align-center">
            <div class="display-1">Staff Lists</div>
        </v-col>
        <v-col cols="12" sm="10" md="6" class="d-flex text-right align-center">
          <v-text-field
            class="flex-grow-1 mr-md-2"
            solo
            placeholder="Search staff information"
            hide-details
            dense
            outlined
            clearable
          />
          <v-btn
            color="primary"
            height="40"
            outlined
            class="ml-1"
          >
            <v-icon left>mdi-folder-search</v-icon>
            Search
          </v-btn>
        </v-col>
      </v-row>
      <v-data-table
        :headers="headers"
        :items="desserts"
        :items-per-page="5"
        class="elevation-1 mt-5"
      >
        <template #[`item.action`]="{ item }">
          <v-row class="pt-1 px-2">
            <v-icon class="ml-1" >
              mdi-eye
            </v-icon>
            <v-icon class="ml-1"> mdi-pencil </v-icon>
            <v-icon class="ml-1" >
              mdi-delete
            </v-icon>
          </v-row>
        </template>
      </v-data-table>
    </v-card>
  </div>

</template>

<script>
export default {
  name: "StaffList",
  data () {
    return {
      headers: [
        {
          text: 'ID',
          align: 'start',
          sortable: false,
          value: 'id',
        },
        { text: 'First Name', value: 'firstName' },
        { text: 'Last Name', value: 'lastName' },
        { text: 'Gender', value: 'gender' },
        { text: 'Position', value: 'position' },
        { text: 'Phone', value: 'phone' },
        { text: 'Address', value: 'address' },
        { text: 'Action', value: 'action' },
      ],
      desserts: [
        {
          id: 1,
          firstName: "dalin",
          lastName: "hoem",
          gender: "female",
          position: "student",
          phone: "0882051005",
          address: "Phnom Penh",
        },
        {
          id: 2,
          firstName: "nalin",
          lastName: "sann",
          gender: "female",
          position: "teacher",
          phone: "0882051005",
          address: "Prey Veng",
        },
      ],
    }
  },
}
</script>

<style scoped>

</style>
