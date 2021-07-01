<template>
  <v-container>
    <v-row>
      <v-col cols="2"> </v-col>
      <v-col cols="8">
        <v-card>
          <v-card-title>Product Details</v-card-title>
          <v-card-text>
            <v-row class="d-flex justify-center ml-1" >
              <v-col>
                <v-row class="d-flex align-center mt-2">
                  <v-col cols="3"> Product Name :</v-col>
                  <v-col cols="9">
                    <v-row>
                      <v-col cols="12" md="6" class="py-0 mt-2 font-weight-bold">
                        Monitor
                      </v-col>
                    </v-row>
                  </v-col>
                </v-row>
                <v-row class="d-flex align-center">
                  <v-col cols="3">Quantity :</v-col>
                  <v-col cols="9">
                    <v-row>
                      <v-col cols="12" md="6" class="py-0 mt-2 font-weight-bold">
                        5
                      </v-col>
                    </v-row>
                  </v-col>
                </v-row>
                <v-row class="d-flex align-center">
                  <v-col cols="3">Date :</v-col>
                  <v-col cols="9">
                    <v-row>
                      <v-col cols="12" md="6" class="py-0 mt-2 font-weight-bold">
                        08-05-2021
                      </v-col>
                    </v-row>
                  </v-col>
                </v-row>
                <v-row class="d-flex align-center">
                  <v-col cols="3">By :</v-col>
                  <v-col cols="9">
                    <v-row>
                      <v-col cols="12" md="6" class="py-0 mt-2 font-weight-bold">
                        Lalisa
                      </v-col>
                    </v-row>
                  </v-col>
                </v-row>
                <v-row class="d-flex align-center mt-2">
                  <v-col cols="3"> Other :</v-col>
                  <v-col cols="9">
                    <v-row>
                      <v-col cols="12" md="6" class="py-0 mt-2 font-weight-bold">
                        ..........
                      </v-col>
                    </v-row>
                  </v-col>
                </v-row>
              </v-col>
            </v-row>
          </v-card-text>
          <v-card-actions>
            <v-spacer></v-spacer>
            <v-btn
              color="info"
              to="/products/list"
            >
              Edit
            </v-btn>
            <v-btn
              color="red"
              type="submit"
              to="/products/list"
            >
              Delete
            </v-btn>
          </v-card-actions>
        </v-card>
      </v-col>
      <v-col cols="2"> </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  name: "details"
}
</script>

<style scoped>

</style>
