<template>
  <div class="d-flex flex-column flex-grow-1">
    <div class="d-flex align-center py-3">
      <v-spacer />
      <v-btn
        color="primary"
        height="40"
        to="/products/register"
      >
        <v-icon left>mdi-account-multiple-plus</v-icon>
        Add new Product
      </v-btn>
    </div>
    <v-card class="pa-2">
      <v-row class="pa-2 align-center justify-content-end">
        <v-col cols="6" sm="2" md="6" class="d-flex text-right align-center">
          <div class="display-1">Product Lists</div>
        </v-col>
        <v-col cols="12" sm="10" md="6" class="d-flex text-right align-center">
          <v-text-field
            class="flex-grow-1 mr-md-2"
            solo
            placeholder="Search product information"
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
    </v-card>
  </div>

</template>

<script>
export default {
  name: "borrows",
  data () {
    return {
      headers: [
        {
          text: 'Product Code',
          align: 'start',
          sortable: false,
          value: 'id',
        },
        { text: 'Product Name', value: 'name' },
        { text: 'Quantity', value: 'quantity' },
        { text: 'Stock In', value: 'stockIn' },
        { text: 'Stock Out', value: 'stockOut' },
        { text: 'Action', value: 'action' },
      ],
      desserts: [
        {
          id: 1,
          name: 'LCD Project',
          quantity: '4',
          stockIn: '8',
          stockOut: '2',
        },
        {
          id: 2,
          name: 'Monitor',
          quantity: '5',
          stockIn: '5',
          stockOut: '0',
        },
        {
          id: 3,
          name: 'Key borad',
          quantity: '14',
          stockIn: '8',
          stockOut: '5',
        },
      ],
    }
  },
}
</script>

<style scoped>

</style>
