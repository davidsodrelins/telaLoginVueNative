<template>
  <view class="quadro">
    <text class="mensagem"> Bem vindo ao sistema</text>
    <text class="usuario"> {{ login }} </text>
  </view>
</template>

<script>
export default {
  props: {
    login: {
      Type: String,
      default: "",
    },
  },

  methods: {
    voltar: function () {
      this.permitido = false;
    },
  },
};
</script>

<style>
.mensagem {
  color: red;
  font-family: Arial, Helvetica, sans-serif;
  font-size: 20px;
  font-weight: 300;
}
.usuario {
  color: rgb(0, 47, 255);
  font-family: Arial, Helvetica, sans-serif;
  font-size: 30px;
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
</style>
