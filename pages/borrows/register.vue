<template>
  <v-container>
    <v-row>
      <v-col cols="3"></v-col>
      <v-col cols="6">
        <v-card class="text-center pa-1" elevation="2" tile>
          <v-card-title class="justify-center display-1 mb-2">
            Borrow Repay
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
                      v-model="borrowId"
                      :rules="borrowIdRules"
                      label="Borrow Id"
                      required
                      dense
                      name="borrowId"
                    />
                  </v-col>
                  <v-col cols="12" sm="6">
                    <v-text-field
                      label="Student Name"
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
                      label="Student Id"
                      v-model="stuId"
                      :rules="stuIdRules"
                      dense
                      required
                      name="stuId"
                    />
                  </v-col>
                </v-row>
                <v-row>
                  <v-col cols="12" sm="12">
                    <v-text-field
                      v-model="Equipment"
                      :rules="equipmentRules"
                      label="Position"
                      dense
                      required
                      name="position"
                    />
                  </v-col>
                </v-row>
                <v-row>
                  <v-col cols="12" sm="12">
                    <v-text-field
                      label="Date"
                      v-model="date"
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
              to="/borrows/list"
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
    borrowId: '',
    name: '',
    stuId: '',
    equipment: '',
    date: '',
    nameRules: [
      v => !!v || 'Student is required',
      v => (v && v.length <= 10) || 'Student must be less than 10 characters',
    ],
    equipmentRules: [
      v => !!v || 'Equipment is required',
      v => (v && v.length <= 10) || 'Equipment must be less than 10 characters',
    ],
    stuIdRules: [
      v => !!v || 'Student Id is required',
      v => (v && v.length <= 10) || 'Student Id must be less than 10 characters',
    ],
    borrowIdRules: [
      v => !!v || 'Borrow Id is required',
      v => (v && v.length <= 20) || 'Phone must be less than 20 characters',
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
