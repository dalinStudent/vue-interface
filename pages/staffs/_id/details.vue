<template>
  <v-container>
    <v-row>
      <v-col cols="2"> </v-col>
      <v-col cols="8">
        <v-card>
          <v-card-title>Staff Details</v-card-title>
          <v-card-text>
            <v-row class="d-flex justify-center ml-1" >
              <v-col>
                <v-row class="d-flex align-center mt-2">
                  <v-col cols="3"> First Name :</v-col>
                  <v-col cols="9">
                    <v-row>
                      <v-col cols="12" md="6" class="py-0 mt-2 font-weight-bold">
                        dalin
                      </v-col>
                    </v-row>
                  </v-col>
                </v-row>
                <v-row class="d-flex align-center">
                  <v-col cols="3"> Last Name :</v-col>
                  <v-col cols="9">
                    <v-row>
                      <v-col cols="12" md="6" class="py-0 mt-2 font-weight-bold">
                        home
                      </v-col>
                    </v-row>
                  </v-col>
                </v-row>
                <v-row class="d-flex align-center">
                  <v-col cols="3">Gender :</v-col>
                  <v-col cols="9">
                    <v-row>
                      <v-col cols="12" md="6" class="py-0 mt-2 font-weight-bold">
                        female
                      </v-col>
                    </v-row>
                  </v-col>
                </v-row>
                <v-row class="d-flex align-center">
                  <v-col cols="3">Email :</v-col>
                  <v-col cols="9">
                    <v-row>
                      <v-col cols="12" md="6" class="py-0 mt-2 font-weight-bold">
                        dalin@gmail.com
                      </v-col>
                    </v-row>
                  </v-col>
                </v-row>
                <v-row class="d-flex align-center mt-2">
                  <v-col cols="3"> Position :</v-col>
                  <v-col cols="9">
                    <v-row>
                      <v-col cols="12" md="6" class="py-0 mt-2 font-weight-bold">
                        student
                      </v-col>
                    </v-row>
                  </v-col>
                </v-row>
                <v-row class="d-flex align-center mt-2">
                  <v-col cols="3"> Phone :</v-col>
                  <v-col cols="9">
                    <v-row>
                      <v-col cols="12" md="6" class="py-0 mt-2 font-weight-bold">
                        0882051005
                      </v-col>
                    </v-row>
                  </v-col>
                </v-row>
                <v-row class="d-flex align-center mt-2">
                  <v-col cols="3"> Address :</v-col>
                  <v-col cols="9">
                    <v-row>
                      <v-col cols="12" md="6" class="py-0 mt-2 font-weight-bold">
                        Prey Venh
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
              to="/staffs/list"
            >
              Edit
            </v-btn>
            <v-btn
              color="red"
              type="submit"
              to="/staffs/list"
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
