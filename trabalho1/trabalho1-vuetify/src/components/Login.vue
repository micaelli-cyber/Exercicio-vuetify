<template>
  <v-container fluid fill-height class="d-flex align-center justify-center" style="min-height: 100vh;">
    <v-card class="elevation-12" max-width="400" width="100%">
      <v-card-title class="text-h5 text-center py-4">
        Login
      </v-card-title>
      <v-card-text>
        <v-form ref="form" v-model="valid" lazy-validation>
          <v-text-field
            label="E-mail"
            v-model="email"
            :rules="emailRules"
            required
            variant="outlined"
            class="mb-4"
          ></v-text-field>

          <v-text-field
            label="Senha"
            type="password"
            v-model="password"
            :rules="passwordRules"
            required
            variant="outlined"
            class="mb-4"
          ></v-text-field>

          <v-btn
            color="primary"
            block
            large
            :disabled="!valid"
            @click="login"
            class="mb-4"
          >
            ENTRAR
          </v-btn>

          <v-btn
            text
            block
            @click="createAccount"
          >
            CRIAR CONTA
          </v-btn>
        </v-form>
      </v-card-text>
    </v-card>
  </v-container>
</template>

<script>
export default {
  name: 'LoginScreen',
  data: () => ({
    valid: true,
    email: '',
    emailRules: [
      v => !!v || 'Campo obrigatório',
      v => /.+@.+\..+/.test(v) || 'E-mail deve ser válido',
    ],
    password: '',
    passwordRules: [
      v => !!v || 'Campo obrigatório',
      v => (v && v.length >= 6) || 'A senha deve ter pelo menos 6 caracteres',
    ],
  }),
  methods: {
    async login() {
      const { valid } = await this.$refs.form.validate();
      if (valid) {
        
        alert('Login attempted with:\nE-mail: ' + this.email + '\nSenha: ' + this.password);
        console.log('Login logic would go here');
      }
    },
    createAccount() {
      
      alert('Redirecionar para tela de Criar Conta');
      console.log('Navigate to create account page');
    },
  },
};
</script>

<style scoped>

</style>
