<template>
    <div class="loginPage">
        <v-card class="card">
          <div class="avatar">
            <v-avatar
              size="80"
            >
              <v-icon class="icon" size="60">
                mdi-account
              </v-icon>
            </v-avatar>
          </div>

            <v-text-field
                class="input"
                v-model="email"
                :error-messages="emailErrors"
                label="E-mail"
                :rules="[rulesEmail.required]"
                required
                @input="$v.email.$touch()"
                @blur="$v.email.$touch()"
                ></v-text-field>

            <v-text-field
                class="input"
                v-model="password"
                :append-icon="showPassWord ? 'mdi-eye' : 'mdi-eye-off'"
                :rules="[rulesPassword.required, rulesPassword.min]"
                :type="showPassWord ? 'text' : 'password'"
                name="input-10-1"
                label="Senha"
                counter
                @click:append="showPassWord = !showPassWord"
            ></v-text-field>

            <div class="GroupButton">
              <CustomButton label="Login"/>
              <div class="forgotPassword">
               <a>Esqueci minha senha</a>
              </div>
            </div>

            <v-divider></v-divider>

            <div class="GroupButton">
              <CustomButton label="Entrar com o Google" icon="mdi-google" showIcon="true"/>
            </div>
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
        email: '',
        password: '',
        rulesPassword: {
          required: value => !!value || 'Digite sua senha',
        },
        rulesEmail: {
          required: value => !!value || 'Digite seu e-mail',
        },
      }
    },
  }
</script>

<style src="./style.scss" lang="scss" scoped></style>