<template>
  <v-container>
    <v-row>
      <v-col cols="3"></v-col>
      <v-col cols="6">
        <v-card class="text-center pa-1" elevation="2" tile>
          <v-card-title class="justify-center display-1 mb-2">
            Register New Product
          </v-card-title>
          <v-card-text>
            <v-form
              ref="form"
              lazy-validation
            >
              <v-container>
                <v-row>
                  <v-col cols="12" sm="6">
                    <v-text-field
                      v-model="productId"
                      :rules="productIdRules"
                      label="Product Id"
                      outlined
                      required
                      dense
                      name="productId"
                    />
                  </v-col>
                  <v-col cols="12" sm="6">
                    <v-text-field
                      label="Product Name"
                      outlined
                      v-model="name"
                      :rules="nameRules"
                      required
                      dense
                      name="name"
                    />
                  </v-col>
                </v-row>
                <v-row>
                  <v-col cols="12" sm="12">
                    <v-text-field
                      label="Quantity"
                      v-model="quantity"
                      :rules="quantityRules"
                      outlined
                      dense
                      required
                      name="stuId"
                    />
                  </v-col>
                </v-row>
                <v-row>
                  <v-col cols="12" sm="12">
                    <v-text-field
                      v-model="date"
                      label="Date"
                      dense
                      required
                      outlined
                      name="date"
                    />
                  </v-col>
                </v-row>
                <v-row>
                  <v-col cols="12" sm="12">
                    <v-text-field
                      label="By"
                      v-model="by"
                      dense
                      required
                      outlined
                      name="by"
                    />
                  </v-col>
                </v-row>
                <v-row>
                  <v-col cols="12" sm="12">
                    <v-text-field
                      label="Other"
                      v-model="other"
                      dense
                      required
                      outlined
                      name="by"
                    />
                  </v-col>
                </v-row>
              </v-container>
            </v-form>
          </v-card-text>
          <v-card-actions>
            <v-spacer></v-spacer>
            <v-btn
              color="warning"
              to="/products/list"
            >
              Cancel
            </v-btn>
            <v-btn
              color="primary"
              type="submit"
              @click="signUp"
            >
              Repay
            </v-btn>
          </v-card-actions>
        </v-card>
      </v-col>
      <v-col cols="3"></v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  name: "register",
  data: () => ({
    productId: '',
    name: '',
    quantity: '',
    by: '',
    other: '',
    date: '',
    nameRules: [
      v => !!v || 'Product is required',
      v => (v && v.length <= 10) || 'Product must be less than 10 characters',
    ],
    quantityRules: [
      v => !!v || 'Quantity is required',
      v => (v && v.length <= 10) || 'Equipment must be less than 10 characters',
    ],
    productIdRules: [
      v => !!v || 'Product Id is required',
      v => (v && v.length <= 10) || 'Product Id must be less than 10 characters',
    ],
  }),
  methods: {
    signUp () {
      this.$refs.form.validate();
    },
  },
}
</script>

<style scoped>

</style>
