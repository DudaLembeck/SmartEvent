<template>
  <ion-page>
    <ion-header :translucent="true">
      <ion-toolbar>
        <ion-title>Perfil</ion-title>
      </ion-toolbar>
    </ion-header>

    <ion-content :fullscreen="true">
      <ion-header collapse="condense">
        <ion-toolbar>
          <ion-title size="large">Blank</ion-title>
        </ion-toolbar>
      </ion-header>

        <ion-button @click="$router.push('/home')"> VOLTAR </ion-button>
      <div class="foto">
       <img src="https://cdn-icons-png.flaticon.com/512/5087/5087607.png" alt="">
       </div>
      <ion-card>
        <ion-card-content>
        <ion-card-header>
                <strong>Bem vindo!</strong>
              </ion-card-header>
               <div class="aa">
            <h2>Dados da conta:</h2>

            <!-- USER -->
            <p><strong>Username:</strong></p>
            <ion-input 
              v-model="login.user" 
              placeholder="Digite seu username"
            ></ion-input>

            <!-- SENHA -->
            <p><strong>Senha:</strong></p>
            <ion-input 
              type="password"
              v-model="login.senha"
              placeholder="Digite sua senha"
            ></ion-input>

          </div>
    <ion-button @click="salvar">Salvar</ion-button>
   
        </ion-card-content>
      </ion-card>

      
    </ion-content>
  </ion-page>
</template>

<script setup lang="ts">
import { IonContent, IonHeader, IonPage, IonTitle, IonToolbar, IonCard, IonCardContent, IonCardHeader, IonButton } from '@ionic/vue';


import { ref } from 'vue'

// 👇 estado do usuário (OBJETO, não array)
const login = ref({
  user: "@algolegalaqui",
  senha: "eusoumuitobom123"
})

// 👇 carregar do localStorage (se existir)
const saved = localStorage.getItem('login')
if (saved) {
  login.value = JSON.parse(saved)
}

// 👇 salvar alterações
const salvar = () => {
  localStorage.setItem('login', JSON.stringify(login.value))
}

</script>

<style scoped>

.foto {
  width: 100%;
  display: flex;
  justify-content: center;
}

ion-card {
  text-align: center;
  left: 0;
  right: 0;
}

strong {
  font-size: 40px;
  color: aliceblue;
  margin: 10px;
}



h2 {
  margin: 20px;
  font-size: 20px;
}

img {
  width: 250px;

}

</style>
