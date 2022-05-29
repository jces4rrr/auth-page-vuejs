<template>
    <div class="loginPage">
        <v-card class="card">

            <v-text-field
                v-model="email"
                :error-messages="emailErrors"
                label="E-mail"
                required
                @input="$v.email.$touch()"
                @blur="$v.email.$touch()"
                ></v-text-field>

            <v-text-field
                v-model="password"
                :append-icon="showPassWord ? 'mdi-eye' : 'mdi-eye-off'"
                :rules="[rules.required, rules.min]"
                :type="showPassWord ? 'text' : 'password'"
                name="input-10-1"
                label="Normal with hint text"
                hint="At least 8 characters"
                counter
                @click:append="showPassWord = !showPassWord"
            ></v-text-field>

            <CustomButton label="Login"/>
        </v-card>
    </div>
</template>

<script>
import CustomButton from '@/components/CustomButton/CustomButton.vue'

  export default {
    components: {
      CustomButton,
    },

    data () {
      return {
        showPassWord: false,
        password: '',
        rules: {
          required: value => !!value || 'Required.',
          min: v => v.length >= 8 || 'Min 8 characters',
          emailMatch: () => (`The email and password you entered don't match`),
        },
      }
    },
  }
</script>

<style src="./style.scss" lang="scss" scoped></style>