<template>
  <v-sheet width="480" elevation="0" class="transparent">
    <v-card class="text-center pa-1" elevation="2" tile>
      <v-card-title class="justify-center display-1 mb-2">
        Sign Up
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
                  v-model="password"
                  type="password"
                  :rules="passwordRules"
                  label="Password"
                  :append-icon="showPassword ? 'mdi-eye' : 'mdi-eye-off'"
                  :type="showPassword ? 'text' : 'password'"
                  @click:append="showPassword = !showPassword"
                  outlined
                  dense
                  required
                  name="password"
                />
              </v-col>
            </v-row>
            <v-row>
              <v-col cols="12" sm="12">
                <v-text-field
                  v-model="password"
                  type="password"
                  :rules="passwordRules"
                  label="Confirm Password"
                  :append-icon="showConfirmPassword ? 'mdi-eye' : 'mdi-eye-off'"
                  :type="showConfirmPassword ? 'text' : 'password'"
                  outlined
                  dense
                  required
                  name="confirmPassword"
                  @click:append="showConfirmPassword = !showConfirmPassword"
                />
              </v-col>
            </v-row>
          </v-container>

          <v-btn
            class="mb-2"
            block
            x-large
            color="primary"
            type="submit"
            @click="signUp"
          >
            Login
          </v-btn>
          <div class="mt-5">
          </div>
        </v-form>
      </v-card-text>
    </v-card>
  </v-sheet>
</template>

<script>

export default {
  layout: 'auth',
  name: 'signup',
  data: () => ({
    firstname: '',
    lastname: '',
    position: '',
    email: '',
    password: '',
    passwordRules: [
      v => !!v || 'Password is required',
      v => /(?=.*\d)(?=.*[a-z])(?=.*[A-Z]).{6,}/.test(v) || 'Password must contain at least lowercase letter, one number, a special character and one uppercase letter',
    ],
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
