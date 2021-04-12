<template>
  <view class="container">
    <text v-if="!permitido" class="bem_vindo"> {{ nome }}</text>
    <text-input v-if="!permitido" class="txt_input" v-model="login" />

    <text-input
      v-if="!permitido"
      class="txt_input"
      type="password"
      v-model="senha"
    />

    <text v-if="!permitido" class="txt_mensagem"> {{ mensagem }}</text>

    <button
      v-if="!permitido"
      class="botao_principal"
      :title="titulo"
      v-bind:on-press="acessar"
    />

    <Principal v-if="permitido" :login="login" />
  </view>
</template>
<script>
import Principal from "./principal";

export default {
  components: { Principal },

  data() {
    return {
      usuarios: [
        { nome: "luã", senha: "l123" },
        { nome: "david", senha: "d999" },
        { nome: "joulbert", senha: "jb23" },
        { nome: "carina", senha: "c512" },
        { nome: "amanda", senha: "a045" },
        { nome: "gabriel", senha: "p483" },
      ],
      nome: "Login",
      titulo: "Acessar",
      login: null,
      senha: null,
      mensagem: null,
      permitido: false,
    };
  },

  methods: {
    acessar: function () {
      if (this.login === "rodrigo" && this.senha === "123456") {
        this.permitido = true;
      } else {
        this.mensagem = "Erro na autenticação";
        this.login = null;
        this.senha = null;
      }
    },
  },
};
</script>

<style>
.txt_input {
  width: 90%;
  border-color: gray;
  border-width: 1;
  padding: 10px;
  margin-top: 10px;
  margin-bottom: 10px;
}

.bem_vindo {
  color: blue;
}

.botao_principal {
  margin-top: 20px;
  color: rgb(53, 76, 109);
  border-radius: 15px;
}

.container {
  background-color: rgb(21, 241, 21);
  align-items: center;
  justify-content: center;
  flex: 1;
}

.text-color-primary {
  color: blue;
}

.txt_mensagem {
  color: red;
}
</style>
