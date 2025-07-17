<template>
  <v-container class="d-flex justify-center align-center" style="height: 100vh; background-color: #121212;">
    <v-card width="400" class="pa-6" color="#212121">
      <v-card-title class="white--text">Cadastro de Banco</v-card-title>
      <v-form>
        <v-text-field
          label="Número do Banco"
          outlined
          dense
          class="mt-2"
        ></v-text-field>

        <v-text-field
          label="Descrição do Banco"
          outlined
          dense
          class="mt-2"
        ></v-text-field>

        <v-switch
          label="Banco Ativo?"
          inset
          class="mt-2"
        ></v-switch>

        <v-btn
          block
          color="#82B1FF"
          class="white--text mt-4"
        >
          SALVAR
        </v-btn>
      </v-form>
    </v-card>
  </v-container>
</template>

<script setup>
</script>
