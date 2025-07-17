<template>
  <v-container class="d-flex justify-center">
    <v-card 
    class="pa-6" 
    style="width: 100%; max-width: 900%;"
    >
    <v-card-title class="text-h5">
        Cadastro de Conta Bancária
    </v-card-title>

      <v-card-text>
        <v-form>

          <v-select
            v-model="banco"
            :items="bancos"
            label="Banco"
            required
          ></v-select>


          <!-- Agência e Dígito -->
          <v-row>
            <v-col cols="8">
              <v-text-field
                v-model="agencia"
                label="Agência"
                required
              ></v-text-field>
            </v-col>
            <v-col cols="4">
              <v-text-field
                v-model="digitoAgencia"
                label="Dígito da Agência"
                required
              ></v-text-field>
            </v-col>
          </v-row>

          <!-- Conta e Dígito -->
          <v-row>
            <v-col cols="8">
              <v-text-field
                v-model="numeroConta"
                label="Número da Conta"
                required
              ></v-text-field>
            </v-col>
            <v-col cols="4">
              <v-text-field
                v-model="digitoConta"
                label="Dígito da Conta"
                required
              ></v-text-field>
            </v-col>
          </v-row>

          <!-- Saldo Inicial -->
          <v-text-field
            v-model="saldoInicial"
            label="Saldo Inicial"
            type="number"
            required
          ></v-text-field>

          <!-- Data de Criação -->
          <v-text-field
            v-model="dataCriacao"
            label="Data de Criação"
            type="date"
            required
          ></v-text-field>

          <!-- Situação -->
          <v-switch
            v-model="contaAtiva"
            label="Conta Ativa"
          ></v-switch>

          <!-- Botão -->
          <v-btn
            color="primary"
            block
            class="mt-4"
            @click="salvarConta"
          >
            SALVAR CONTA
          </v-btn>
        </v-form>
      </v-card-text>
    </v-card>
  </v-container>
</template>

<script>
export default {
  name: 'CadastroConta',
  data() {
    return {
      banco: null,
      bancos: [
        'Banco do Brasil',
        'Caixa Econômica Federal',
        'Itaú',
        'Bradesco'
      ],
      agencia: '',
      digitoAgencia: '',
      numeroConta: '',
      digitoConta: '',
      saldoInicial: '',
      dataCriacao: '',
      contaAtiva: true
    };
  },
  methods: {
    salvarConta() {
      console.log({
        banco: this.banco,
        agencia: this.agencia,
        digitoAgencia: this.digitoAgencia,
        numeroConta: this.numeroConta,
        digitoConta: this.digitoConta,
        saldoInicial: this.saldoInicial,
        dataCriacao: this.dataCriacao,
        contaAtiva: this.contaAtiva
      });
      alert('Conta salva com sucesso!');
    }
  }
};
</script>
