<template>
  <v-container>
    <v-row>
      <v-col cols="3"></v-col>
      <v-col cols="6">
        <v-card class="text-center pa-1" elevation="2" tile>
          <v-card-title class="justify-center display-1 mb-2">
            Edit Staff Information
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
                      v-model="firstname"
                      :rules="nameRules"
                      label="First Name"
                      outlined
                      required
                      dense
                      name="firstName"
                    />
                  </v-col>
                  <v-col cols="12" sm="6">
                    <v-text-field
                      label="Last Name"
                      v-model="lastname"
                      :rules="nameRules"
                      outlined
                      required
                      dense
                      name="lastName"
                    />
                  </v-col>
                </v-row>
                <v-row>
                  <v-col cols="12" sm="12">
                    <v-select
                      :items="genders"
                      label="Outlined style"
                      dense
                      outlined
                    ></v-select>
                  </v-col>
                </v-row>
                <v-row>
                  <v-col cols="12" sm="12">
                    <v-text-field
                      label="Email"
                      v-model="email"
                      :rules="emailRules"
                      outlined
                      dense
                      required
                      name="email"
                    />
                  </v-col>
                </v-row>
                <v-row>
                  <v-col cols="12" sm="12">
                    <v-text-field
                      v-model="position"
                      :rules="positionRules"
                      label="Position"
                      outlined
                      dense
                      required
                      name="position"
                    />
                  </v-col>
                </v-row>
                <v-row>
                  <v-col cols="12" sm="12">
                    <v-text-field
                      label="Phone"
                      v-model="phone"
                      :rules="phoneRules"
                      outlined
                      dense
                      required
                      name="phone"
                    />
                  </v-col>
                </v-row>
                <v-row>
                  <v-col cols="12" sm="12">
                    <v-text-field
                      label="Address"
                      v-model="address"
                      :rules="addressRules"
                      outlined
                      dense
                      required
                      name="phone"
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
              to="/staffs/list"
            >
              Cancel
            </v-btn>
            <v-btn
              color="primary"
              type="submit"
              @click="signUp"
            >
              Update
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
  name: "edit",
  data: () => ({
    firstname: '',
    lastname: '',
    position: '',
    genders: ['Female', 'Male'],
    email: '',
    phone: '',
    address: '',
    emailRules: [
      v => !!v || 'E-mail is required',
      v => /^(([^<>()[\]\\.,;:\s@']+(\.[^<>()\\[\]\\.,;:\s@']+)*)|('.+'))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,}))$/.test(v) || 'E-mail must be valid',
    ],
    nameRules: [
      v => !!v || 'Name is required',
      v => (v && v.length <= 10) || 'Name must be less than 10 characters',
    ],
    positionRules: [
      v => !!v || 'Position is required',
      v => (v && v.length <= 10) || 'Position must be less than 10 characters',
    ],
    phoneRules: [
      v => !!v || 'Phone is required',
      v => (v && v.length <= 10) || 'Position must be less than 10 characters',
    ],
    addressRules: [
      v => !!v || 'Phone is required',
      v => (v && v.length <= 10) || 'Position must be less than 10 characters',
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
