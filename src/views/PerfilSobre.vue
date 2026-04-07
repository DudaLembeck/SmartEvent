<template>
  <ion-page>
    <ion-header :translucent="true">
      <ion-toolbar>
        <ion-title>Blank</ion-title>
      </ion-toolbar>
    </ion-header>

    <ion-content :fullscreen="true">
      <ion-header collapse="condense">
        <ion-toolbar>
          <ion-title size="large">Blank</ion-title>
        </ion-toolbar>
      </ion-header>
       <img src="https://cdn-icons-png.flaticon.com/512/5087/5087607.png" alt="">
      <ion-card>
        <ion-card-content>
        <ion-card-header>
                <strong>Bem vindo!</strong>
              </ion-card-header>
                <h1>Dados da conta:</h1>
                <h1>Username: {{  }}

                </h1>
                <h1>Senha:

                </h1>
   
        </ion-card-content>
      </ion-card>

      
    </ion-content>
  </ion-page>
</template>

<script setup lang="ts">
import { IonContent, IonHeader, IonPage, IonTitle, IonToolbar, IonCard, IonCardContent, IonCardHeader } from '@ionic/vue';



</script>

<style scoped>
ion-card {
  text-align: center;
  left: 0;
  right: 0;
}

strong {
  font-size: 40px;
}

img {
  width: 230px;

}

</style>
