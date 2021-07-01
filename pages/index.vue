<template>
  <v-sheet width="480" elevation="0" class="transparent">
    <v-card class="text-center pa-1" elevation="2" tile>
      <v-card-title class="justify-center display-1 mb-2">
        Login
      </v-card-title>
      <v-card-text>
        <v-form
          ref="form"
        >
          <v-text-field
            label="Email"
            outlined
            required
            dense
            name="email"
          />
          <v-text-field
            label="Password"
            :append-icon="showPassword ? 'mdi-eye' : 'mdi-eye-off'"
            :type="showPassword ? 'text' : 'password'"
            @click:append="showPassword = !showPassword"
            outlined
            dense
            required
            name="password"
          />
          <v-btn
            class="mb-2"
            block
            x-large
            color="primary"
            type="submit"
          >
            Login
          </v-btn>
          <div class="mt-5">
          </div>
        </v-form>
      </v-card-text>
    </v-card>
    <div class="text-center mt-6">
      <NuxtLink to="/auth/forgot-password"> Forgot Password</NuxtLink>
    </div>
    <div class="text-center mt-6">
      <NuxtLink to="/auth/signup"> Create an account?</NuxtLink>
    </div>
  </v-sheet>
</template>

<script>
export default {
  layout: 'auth',
  name: 'signin',
  data() {
    return {
      showPassword: false,
    }
  }
}
</script>

<style scoped>

</style>
