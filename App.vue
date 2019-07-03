<template>
  <v-app>
    <v-content>
      <img alt="Vue logo" src="./assets/logo.png" />
      <v-form ref="form" v-model="accept" lazy-validation>
        <v-layout row justify-center class="mt-5" wrap>
          <v-flex xs12 md5>
            <v-text-field
              label="Name"
              :value="generalApplicantInfo.name"
              @change="v => generalApplicantInfo.name = v"
              :rules="[rules.required]"
              required
            ></v-text-field>
            <v-text-field
              label="Surname"
              :value="generalApplicantInfo.surName"
              @change="v => generalApplicantInfo.surName = v"
              :rules="[rules.required]"
              required
            ></v-text-field>
          </v-flex>
        </v-layout>
      </v-form>
    </v-content>
  </v-app>
</template>

<script>
export default {
  name: 'app',
  data: () => ({
    accept: true,
    generalApplicantInfo: {
      gender: '',
      name: '',
      surName: ''
    },
    rules: {
      required: value => !!value || 'field is required'
    }
  })
}
</script>

<style>
#app {
  /* font-family: 'Avenir', Helvetica, Arial, sans-serif; */
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  /* color: #2c3e50; */
  background-color: #004566;
  margin-top: 60px;
}
</style>
